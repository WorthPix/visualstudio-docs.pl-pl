---
title: 'Porady: pobieranie usługi | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- services, consuming
ms.assetid: 1f000020-8fb7-4e39-8e1e-2e38c7fec3d4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b4805c3b9ceb62dbc790af7b1191a13476c27c9a
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39636770"
---
# <a name="how-to-get-a-service"></a>Porady: uzyskiwanie usługi
Często muszą uzyskać dostęp do różnych funkcji usług Visual Studio. Ogólnie rzecz biorąc usługa Visual Studio zawiera jeden lub więcej interfejsów, które są dostępne. Większość usług można uzyskać z pakietu VSPackage.  
  
 Dowolnego pakietu VSPackage, który pochodzi od klasy <xref:Microsoft.VisualStudio.Shell.Package> i ma, poprawnie ulokowany może poprosić o dowolnej usługi globalne. Ponieważ `Package` klasy implementuje <xref:System.IServiceProvider>, dowolnego pakietu VSPackage, który pochodzi od klasy `Package` jest również dostawcę usług.  
  
 Po załadowaniu programu Visual Studio <xref:Microsoft.VisualStudio.Shell.Package>, przekazuje on <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> obiekt <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> metody podczas inicjowania. Jest to nazywane *lokalizacji* pakietu VSPackage. `Package` Klasy otacza tego dostawcy usług i zapewnia <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> metodę pobierania usługi.  
  
## <a name="getting-a-service-from-an-initialized-vspackage"></a>Pobieranie usługi z zainicjowane pakietu VSPackage  
  
1.  Każde rozszerzenie programu Visual Studio rozpoczyna się od Projekt wdrożenia VSIX, który będzie zawierać zasoby rozszerzenia. Tworzenie [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu VSIX, o nazwie `GetServiceExtension`. Można znaleźć szablonu projektu VSIX w **nowy projekt** , okno dialogowe **Visual C#** > **rozszerzalności**.  
  
2.  Teraz Dodaj polecenie niestandardowe szablon elementu o nazwie **GetServiceCommand**. W **Dodaj nowy element** okno dialogowe, przejdź do **Visual C#** > **rozszerzalności** i wybierz **polecenia niestandardowego**. W **nazwa** u dołu okna, Zmień nazwę pliku polecenia, aby *GetServiceCommand.cs*. Aby uzyskać więcej informacji o sposobie tworzenia niestandardowych poleceń [Tworzenie rozszerzenia za pomocą polecenia menu](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
3.  W *GetServiceCommand.cs*, Usuń treść `MenuItemCommand` metody i Dodaj następujący kod:  
  
    ```csharp  
    IVsActivityLog activityLog = ServiceProvider.GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (activityLog == null) return;  
    System.Windows.Forms.MessageBox.Show("Found the activity log service.");  
  
    ```  
  
     Ten kod pobiera usługi SVsActivityLog i rzutuje je na <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> interfejs, który może służyć do zapisu w dzienniku aktywności. Aby uzyskać przykład, zobacz [porady: Korzystanie z dziennika aktywności](../extensibility/how-to-use-the-activity-log.md).  
  
4.  Skompiluj projekt, a następnie rozpocząć debugowanie. Zostanie wyświetlone wystąpienie eksperymentalne.  
  
5.  Na **narzędzia** znaleźć menu wystąpienie eksperymentalne **wywołania GetServiceCommand** przycisku. Po kliknięciu tego przycisku, powinien zostać wyświetlony komunikat informujący, że **znaleziono działanie usługi rejestrowania.**  
  
## <a name="getting-a-service-from-a-tool-window-or-control-container"></a>Wprowadzenie usługi z kontenera narzędzia okna lub kontrolki  
 Czasami może być konieczne uzyskiwanie usługi okno narzędzia lub kontroli kontenera, które nie zostały zlokalizowane; w przeciwnym razie ma zostały umieszczone u dostawcy usług, które nie wie o usługę, którą chcesz. Na przykład można zapisywać w dzienniku aktywności ze znajdujących się pod kontrolą.  
  
 Statyczne <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> metoda korzysta z pamięci podręcznej usługodawcy, który jest zainicjowany po raz pierwszy pochodną dowolnego pakietu VSPackage <xref:Microsoft.VisualStudio.Shell.Package> jest ulokowany.  
  
 Ponieważ Konstruktor pakietu VSPackage jest wywoływana przed jest ulokowany pakietu VSPackage, usługi global services są zwykle dostępne z w Konstruktorze pakietu VSPackage. Zobacz [porady: Rozwiązywanie problemów z usługami](../extensibility/how-to-troubleshoot-services.md) obejście tego problemu.  
  
 Oto przykład sposobu, w jaki można pobrać usługi w okno narzędzia lub innego elementu innego niż pakietu VSPackage.  
  
```csharp  
IVsActivityLog log = Package.GetGlobalService(typeof(SVsActivityLog)) as IVsActivityLog;  
if (log == null) return;  
```  
  
## <a name="getting-a-service-from-the-dte-object"></a>Wprowadzenie usługi z obiektu DTE  
 Możesz też pobrać usług <xref:EnvDTE.DTEClass> obiektu. Jednakże, należy uzyskać obiekt DTE jako usługa z pakietu VSPackage lub przez wywołanie statycznego <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> metody.  
  
 Implementuje obiekt DTE <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>, które służy do wykonywania zapytań dla usługi przy użyciu <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A>.  
  
 Oto jak uzyskać usługę z obiektu DTE.  
  
```csharp  
// Start with the DTE object, for example:   
// using EnvDTE;  
// DTE dte = (DTE)GetService(typeof(DTE));  
  
ServiceProvider sp = new ServiceProvider((Microsoft.VisualStudio.OLE.Interop.IServiceProvider)dte);  
if (sp != null)  
{  
    IVsActivityLog log = sp.GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log != null)  
    {   
        System.Windows.Forms.MessageBox.Show("Found the activity log service.");  
    }  
}  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Porady: świadczenia usług](../extensibility/how-to-provide-a-service.md)   
 [Użyj i świadczenia usług](../extensibility/using-and-providing-services.md)   
 [Podstawowe informacje o usłudze](../extensibility/internals/service-essentials.md)