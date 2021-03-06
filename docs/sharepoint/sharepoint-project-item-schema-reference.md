---
title: Odwołanie do schematu elementu projektu SharePoint | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FeatureProperty element
- SafeControls element
- SafeControl element
- .spdata files
- ExtensionData element
- FeatureProperties element
- ProjectOutputFile element
- Files element
- ProjectItemFolder element
- ProjectItemFile element
- ExtensionDataItem element
- ProjectItem element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b94856d4e00cd15f324040ccd49c90bb1be29a7d
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120285"
---
# <a name="sharepoint-project-item-schema-reference"></a>Odwołanie do schematu elementu projektu SharePoint
  Visual Studio będzie korzystać schematu elementu projektu SharePoint do sprawdzania poprawności zawartości *.spdata —* plików. *.Spdata —* plik Określa zawartości i zachowanie elementu projektu SharePoint. Aby uzyskać więcej informacji o zawartości programu SharePoint — elementy projektu, zobacz [elementu Tworzenie szablonów i szablonów projektu dla elementów projektu SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 Schemat elementu projektu SharePoint o nazwie ProjectItemModelSchema.xsd i jest instalowany domyślnie w lokalizacji % Program Files (11.0\Xml\Schemas x86)%\Microsoft programu Visual Studio.  
  
 Element główny jest [ProjectItem](../sharepoint/projectitem-element.md) elementu. W poniższej tabeli opisano wszystkie elementy z definicją w schemacie.  
  
|Element|Opis|  
|-------------|-----------------|  
|[Extensiondata —](../sharepoint/extensiondata-element.md)|Reprezentuje kolekcję elementów danych niestandardowych, które są skojarzone z elementem projektu programu SharePoint.|  
|[Extensiondataitem —](../sharepoint/extensiondataitem-element.md)|Reprezentuje element danych niestandardowych, który jest skojarzony z elementem projektu programu SharePoint, w formacie klucza i wartości. Klucz i wartość muszą być ciągami.|  
|[Featureproperties —](../sharepoint/featureproperties-element.md)|Reprezentuje kolekcję wartości właściwości, które są dołączone do funkcji po wdrożeniu programu SharePoint. Po wdrożeniu funkcji można uzyskać dostępu do wartości właściwości, w kodzie.|  
|[FeatureProperty —](../sharepoint/featureproperty-element.md)|Reprezentuje właściwości niestandardowej, która jest zawarta w funkcji po wdrożeniu programu SharePoint. Po wdrożeniu funkcji można uzyskać dostępu do właściwości, w kodzie.|  
|[Pliki](../sharepoint/files-element.md)|Określa pliki do wdrożenia z elementu projektu SharePoint, takich jak plik element funkcji lub wyjście projektu.|  
|[ProjectItem](../sharepoint/projectitem-element.md)|Reprezentuje element projektu programu SharePoint.|  
|[Projectitemfile —](../sharepoint/projectitemfile-element.md)|Reprezentuje plik programu SharePoint, takich jak plik element funkcji, aby dołączyć z elementem projektu po wdrożeniu programu SharePoint.|  
|[Projectitemfolder —](../sharepoint/projectitemfolder-element.md)|Reprezentuje zamapowany folder.|  
|[Projectoutputfile —](../sharepoint/projectoutputfile-element.md)|Reprezentuje dane wyjściowe projektu do dołączenia do elementu projektu po wdrożeniu programu SharePoint.|  
|[SafeControl —](../sharepoint/safecontrol-element.md)|Reprezentuje kontrolki ASPX lub składnik Web Part jest oznaczony jako bezpieczny dla każdego użytkownika uzyskiwać dostęp do dowolnej strony ASPX w witrynie programu SharePoint.|  
|[SafeControls —](../sharepoint/safecontrols-element.md)|Reprezentuje kolekcję ASPX kontrolek i składników Web Part, które są wyznaczone jako bezpieczne dla każdego użytkownika uzyskiwać dostęp do dowolnej strony ASPX w witrynie programu SharePoint.|  
  
## <a name="see-also"></a>Zobacz także
 [Tworzenie szablonów elementów i szablonów projektu dla SharePoint — elementy projektu](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)  
  
