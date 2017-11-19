---
title: "Uruchamianie kompilacji w środowisku IDE | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: build
ms.assetid: 936317aa-63b7-4eb0-b9db-b260a0306196
caps.latest.revision: "5"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 081bcfd01d8c28959bf0dd4d038e91895e9c3983
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="starting-a-build-from-within-the-ide"></a>Uruchamianie kompilacji w środowisku IDE
Systemów projektów niestandardowych należy użyć <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildManagerAccessor> można uruchomić kompilacji. W tym temacie opisano to i opisano procedury.  
  
## <a name="parallel-builds-and-threads"></a>Równoległych kompilacji i wątków  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Umożliwia równoległe kompilacje, które wymaga pośrednictwa do uzyskiwania dostępu do wspólnych zasobów. Systemy projektu można uruchomić kompilacji asynchronicznie, ale systemy te nie mogą wywoływać funkcje kompilacji z wewnątrz wywołania podano tworzy kopię z menedżerem kompilacji.  
  
 Jeśli system projektu modyfikuje zmienne środowiskowe, musi on ustawiony NodeAffinity kompilacji OutOfProc. Oznacza to, nie można użyć obiektów hosta, ponieważ wymagają one węzła wewnątrzprocesową.  
  
## <a name="using-ivsbuildmanageraccessor"></a>Przy użyciu IVSBuildManagerAccessor  
 Poniższy kod przedstawia metodę system projektu można użyć do uruchomienia kompilacji:  
  
```csharp
  
public bool Build(Project project, bool isDesignTimeBuild)  
{  
    // Get the accessor from the IServiceProvider interface for the   
    // project system  
    IVsBuildManagerAccessor accessor =  
        serviceProvider.GetService(typeof(SVsBuildManagerAccessor)) as     
        IVsBuildManagerAccessor;  
    bool releaseUIThread = false;  
    try  
    {  
        if(accessor != null)  
        {  
            // Claim the UI thread under the following conditions:  
            // 1. The build must use a resource that uses the UI thread  
            // or,  
            // 2. The build requires the in-proc node AND waits on the   
            // UI thread for the build to complete  
            if(NeedsUIThread)  
            {  
                int result = accessor.ClaimUIThreadForBuild();  
                if(result != S_OK)  
                {  
                     // Not allowed to claim the UI thread right now  
                     return false;  
                }  
                releaseUIThread = true;  
             }  
             if(isDesignTimeBuild)  
             {  
// Start the design time build  
                  int result = accessor.BeginDesignTimeBuild();  
                  if(result != S_OK)  
                  {  
                      // Not allowed to begin a design-time build at  
                      // this time. Try again later.  
                      return false;  
                  }  
             }  
         }  
         bool buildSucceeded = false;  
         // perform project-system specific build set up tasks  
         // Create your BuildRequestData  
         // This assumes a IHostServices variable (hostServices) set   
   // to your host services. If you don't use a project instance   
         // (you build from a file for example) then use another   
         // constructor.  
         BuildRequestData requestData = new   
             BuildRequestData(project.CreateProjectInstance(),   
             "myTarget", hostServices,   
             BuildRequestData.BuildRequestDataFlags.None);  
         // Mark your your submission as Pending  
         BuildSubmission submission =  
              BuildManager.DefaultBuildManager.  
              PendBuildRequest(requestData);  
         // Register the loggers in BuildLoggers  
         if (accessor != null)  
         {  
               foreach (ILogger logger in BuildLoggers)  
               {  
                    accessor.RegisterLogger(submission.SubmissionId,   
                        logger);  
               }  
         }  
         BuildResult buildResult = submission.Execute();  
         return buildResult;  
     }  
     // Clean up resources  
     finally  
     {  
         if(accessor != null)  
         {  
             // Unregister the loggers, if necessary.  
             accessor.UnregisterLoggers(submission.SubmissionId);  
             // Release the UI thread, if used  
             if(releaseUIThread)  
             {  
                  accessor.ReleaseUIThreadForBuild();  
             }  
             // End the design time build, if used  
             if(isDesignTimeBuild)  
             {  
                  accessor.EndDesignTimeBuild();  
             }  
         }  
     }  
}  
  
```