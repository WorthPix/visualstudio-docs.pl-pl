---
title: Findunderpath — zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#FindUnderPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, FindUnderPath task
- FindUnderPath task [MSBuild]
ms.assetid: 3c6d58b0-36e8-47aa-bfca-b73dd2045d91
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c1f7ea93011878e9e47a5daa843a71d904318ce4
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/10/2018
ms.locfileid: "37946524"
---
# <a name="findunderpath-task"></a>FindUnderPath — zadanie
Określa, które elementy w kolekcji określonego elementu mają ścieżek, które znajdują się w lub pod określonym folderze.  
  
## <a name="parameters"></a>Parametry  
 W poniższej tabeli opisano parametry `FindUnderPath` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`Files`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Określa pliki, których ścieżki powinny zostać porównane z ścieżka określona przez plik `Path` parametru.|  
|`InPath`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Zawiera elementy, które zostały znalezione w określonej ścieżce.|  
|`OutOfPath`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Zawiera elementy, które nie zostały odnalezione w określonej ścieżce.|  
|`Path`|Wymagane <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Określa ścieżkę folderu, do użycia jako odwołanie.|  
|`UpdateToAbsolutePaths`|Opcjonalnie `Boolean` parametru.<br /><br /> W przypadku opcji true ścieżki elementów wyjściowych są zaktualizowane pod kątem ścieżek bezwzględnych.|  
  
## <a name="remarks"></a>Uwagi  
 Oprócz parametrów wymienionych powyżej, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto `FindUnderPath` zadanie, aby określić, jeśli pliki zawarte w `MyFiles` elementów ma ścieżki, które istnieją w ścieżce określonej przez `SearchPath` właściwości. Po zakończeniu zadania, `FilesNotFoundInPath` element zawiera *więc Plik1.txt* pliku, a `FilesFoundInPath` element zawiera *Plik2.txt* pliku.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <MyFiles Include="C:\File1.txt" />  
        <MyFiles Include="C:\Projects\MyProject\File2.txt" />  
    </ItemGroup>  
  
    <PropertyGroup>  
        <SearchPath>C:\Projects\MyProject</SearchPath>  
    </PropertyGroup>  
  
    <Target Name="FindFiles">  
        <FindUnderPath  
            Files="@(MyFiles)"  
            Path="$(SearchPath)">  
            <Output  
                TaskParameter="InPath"  
                ItemName="FilesFoundInPath" />  
            <Output  
                TaskParameter="OutOfPath"  
                ItemName="FilesNotFoundInPath" />  
        </FindUnderPath>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)   
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Pojęcia dotyczące programu MSBuild](../msbuild/msbuild-concepts.md)