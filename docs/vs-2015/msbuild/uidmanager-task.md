---
title: Uidmanager — zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UidManager task [WPF MSBuild]
- UidManager task [WPF MSBuild], parameters
- managing UIDs when localizing XAML elements [WPF MSBuild]
- localizing XAML elements [WPF MSBuild], managing UIDs
- checking UIDs when localizing XAML elements [WPF MSBuild]
ms.assetid: 4fc7b5a5-11b0-46ca-9656-8c2a0b08d1fe
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa51ddb8f2cf6e200b7313069fca3ee6db3ebcf3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49208068"
---
# <a name="uidmanager-task"></a>UidManager — Zadanie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
<xref:Microsoft.Build.Tasks.Windows.UidManager> Zadanie sprawdza, aktualizuje lub usuwa unikatowe identyfikatory (UID), aby zlokalizować wszystkie [!INCLUDE[TLA#tla_xaml](../includes/tlasharptla-xaml-md.md)] elementy, które znajdują się w źródle [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] plików.  
  
## <a name="task-parameters"></a>Parametry zadania  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`IntermediateDirectory`|Opcjonalnie **ciąg** parametru.<br /><br /> Określa katalog, który służy do tworzenia kopii zapasowej źródła [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] pliki, które są określone przez **MarkupFiles** parametru.|  
|`MarkupFiles`|Wymagane **[] ITaskItem** parametru.<br /><br /> Określa źródło [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] pliki do dołączenia do UID sprawdzania, aktualizowania lub usuwania.|  
|`Task`|Wymagane **ciąg** parametru.<br /><br /> Określa zadanie zarządzania UID, które chcesz wykonać. Prawidłowe opcje to **Sprawdź**, **aktualizacji**, lub **Usuń**.|  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto <xref:Microsoft.Build.Tasks.Windows.UidManager> zadania, aby sprawdzić, czy określone źródło [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] pliki zawierają [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] elementy, które mają odpowiednie UID.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.UidManager"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="UidManagerTask">  
    <UidManager  
      Task="Check"  
      MarkupFiles="Page1.xaml;Page2.xaml"  
      IntermediateDirectory="c:\UidManagerIntermediateDirectory" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do WPF MSBuild](../msbuild/wpf-msbuild-reference.md)   
 [Odwołanie do zadania](../msbuild/wpf-msbuild-task-reference.md)   
 [Odwołanie do narzędzia MSBuild](../msbuild/msbuild-reference.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)   
 [Kompilowanie aplikacji WPF (WPF)](http://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)   
 [Porady: lokalizowanie aplikacji](http://msdn.microsoft.com/library/5001227e-9326-48a4-9dcd-ba1b89ee6653)



