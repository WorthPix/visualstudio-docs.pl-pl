---
title: CreateProperty — zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#CreateProperty
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CreateProperty task [MSBuild]
- MSBuild, CreateProperty task
ms.assetid: fbc31a88-62d4-43d2-b739-68ef3fac38f5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4843262862501377fd3740639d6a22a79e77879d
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/10/2018
ms.locfileid: "37946348"
---
# <a name="createproperty-task"></a>CreateProperty — zadanie
Zostaną wyświetlone wszystkie właściwości wartości przekazane. Dzięki temu wartości, które mają być kopiowane z jedną właściwość lub ciągu do innego.  
  
## <a name="attributes"></a>Atrybuty  
 W poniższej tabeli opisano parametry `CreateProperty` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`Value`|Opcjonalnie `String` parametr wyjściowy.<br /><br /> Określa wartość do skopiowania do nowej właściwości.|  
|`ValueSetByTask`|Opcjonalnie `String` parametr wyjściowy.<br /><br /> Zawiera taką samą wartość jak `Value` parametru. Użyj tego parametru, tylko wtedy, gdy chcesz uniknąć dane wyjściowe właściwością [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] po pomija otaczającego element docelowy, ponieważ dane wyjściowe są aktualne.|  
  
## <a name="remarks"></a>Uwagi  
 Oprócz parametrów wymienionych powyżej, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto `CreateProperty` zadania do utworzenia `NewFile` przy użyciu kombinacji wartości właściwości `SourceFilename` i `SourceFileExtension` właściwości.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <PropertyGroup>  
        <SourceFilename>Module1</SourceFilename>  
        <SourceFileExtension>vb</SourceFileExtension>  
    </PropertyGroup>  
  
    <Target Name="CreateProperties">  
  
        <CreateProperty  
            Value="$(SourceFilename).$(SourceFileExtension)">  
            <Output  
                TaskParameter="Value"  
                PropertyName="NewFile" />  
        </CreateProperty>  
  
    </Target>  
  
</Project>  
```  
  
 Po uruchomieniu projektu, a wartość `NewFile` właściwość *Module1.vb*.  
  
## <a name="see-also"></a>Zobacz także  
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)   
 [Zadania](../msbuild/msbuild-tasks.md)