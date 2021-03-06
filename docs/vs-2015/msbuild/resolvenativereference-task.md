---
title: Resolvenativereference — zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ResolveNativeReference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ResolveNativeReference task
- ResolveNativeReference task [MSBuild]
ms.assetid: 56acd101-de77-4eec-92c6-f5c6d2187579
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a874055e5af1a0aafd48296a99f12a83d56369f8
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49281314"
---
# <a name="resolvenativereference-task"></a>ResolveNativeReference — Zadanie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Usuwa odwołania natywne. Implementuje <xref:Microsoft.Build.Tasks.ResolveNativeReference> klasy. Ta klasa obsługuje infrastrukturę .NET Framework, która nie jest przeznaczona do użycia bezpośrednio w kodzie.  
  
## <a name="task-parameters"></a>Parametry zadania  
 W poniższej tabeli opisano parametry `ResolveNativeReference` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`AdditionalSearchPaths`|Wymagane [String] (<!-- TODO: review code entity reference <xref:assetId:///String?qualifyHint=False&amp;autoUpgrade=True>  -->)`[]` parametru.<br /><br /> Pobiera lub ustawia Przeszukuj ścieżki pod kątem rozpoznawania tożsamości zestawu odwołania natywne.|  
|`ContainedComComponents`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Pobiera lub ustawia składników COM natywnego zestawu.|  
|`ContainedLooseEtcFiles`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Pobiera lub ustawia luźne pliki Etc na liście natywny manifest.|  
|`ContainedLooseTlbFiles`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Pobiera lub ustawia plików .tlb luźne natywny zestaw.|  
|`ContainedPrerequisiteAssemblies`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Pobiera lub ustawia zestawów, które musi znajdować się przed użyciem manifestu.|  
|`ContainedTypeLibraries`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Pobiera lub ustawia biblioteki typu zestawu macierzystego.|  
|`ContainingReferenceFiles`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Pobiera lub ustawia pliki odwołań.|  
|`NativeReferences`|Wymagany parametr interfejsu <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Pobiera lub ustawia odwołania do zestawów natywnych Win32.|  
  
## <a name="remarks"></a>Uwagi  
 Oprócz parametrów wymienionych powyżej, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)



