---
title: Projectoutputfile — Element | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectOutputFile element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 99f8173da22f631a1be74c18d4312f74958259e9
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120308"
---
# <a name="projectoutputfile-element"></a>ProjectOutputFile — element
  Reprezentuje dane wyjściowe oddzielny projekt zawierający element projektu po wdrożeniu programu SharePoint.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<ProjectOutputFile ProjectId = "GUID of the project"  
    ProjectPath = "Relative path of the project"  
    Target = "Deployment path of the project output"  
    Type = "Type of deployment for the project output" />  
```  
  
## <a name="type"></a>Typ  
 **ProjectOutputFileType**  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|**Identyfikator projektu**|Wymagane **xs:string** atrybutu.<br /><br /> Identyfikator GUID projektu zależnych, który zawiera dane wyjściowe, które chcesz dołączyć. Odpowiada to **ProjectGuid** elementu w pliku projektu zależnych.|  
|**ProjectPath**|Wymagane **xs:string** atrybutu.<br /><br /> Ścieżka względna, łącznie z nazwą pliku projektu, zależnych projektu, którego dane wyjściowe, które chcesz dołączyć. Ta ścieżka jest określana względem folderze głównym projektu programu SharePoint, który zawiera element projektu programu SharePoint.|  
|**Docelowy**|Opcjonalne **xs:string** atrybutu.<br /><br /> Ścieżka, gdzie ma zostać wdrożona na serwerze programu SharePoint odnoszącego się do folderu głównego wdrożenia wyjście projektu zależnych. Folder główny wdrożenia jest określana przez typ wdrożenia, określony przez **typu** atrybutu.<br /><br /> Aby uzyskać więcej informacji, zobacz opisy **Deployment ścieżkę** i **główny wdrożenia** właściwości programu SharePoint projektu elementów w [rozwiązań SharePoint opracowanie](../sharepoint/developing-sharepoint-solutions.md).|  
|**Typ**|Wymagane **xs:string** atrybutu.<br /><br /> Typ wdrożenia do użycia dla danych wyjściowych projektu zależnych. Aby uzyskać więcej informacji na temat możliwych wartości, zobacz opis **typu wdrożenia** właściwości SharePoint — elementy projektu w [rozwiązań SharePoint opracowanie](../sharepoint/developing-sharepoint-solutions.md).|  
  
### <a name="child-elements"></a>Elementy podrzędne
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne
  
|Element|Opis|  
|-------------|-----------------|  
|[Pliki](../sharepoint/files-element.md)|Określa pliki do dołączenia do elementu projektu SharePoint po wdrożeniu programu SharePoint.|  
  
## <a name="remarks"></a>Uwagi  
 Użyj **projectoutputfile —** element, aby dołączyć dane wyjściowe projektu wdrażania elementu projektu SharePoint. Możesz określić inny projekt lub tego samego projektu, który zawiera element projektu. Aby uzyskać więcej informacji, zobacz [zawierają informacje pakowania i wdrażania w elementach projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Informacje o elementach
  
|||  
|-|-|  
|**Namespace**|http<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|  
|**Nazwa schematu**|Schemat elementu projektu SharePoint|  
|**Sprawdzanie poprawności pliku**|ProjectItemModelSchema.xsd|  
|**Może być pusta.**|Nie|  
  
## <a name="see-also"></a>Zobacz także
 [Odwołanie do schematu elementu projektu SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Podaj informacje pakowania i wdrażania w elementach projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [Tworzenie rozwiązań programu SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
