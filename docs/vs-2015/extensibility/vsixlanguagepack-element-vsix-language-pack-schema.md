---
title: Element VSIXLanguagePack (VSIX Language Pack schemat) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 767f5c22-8b87-49ca-92aa-a7a3f026469f
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8cc63f24f50f8ed0fecb9640ae4b2a5d2ec669be
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49224747"
---
# <a name="vsixlanguagepack-element-vsix-language-pack-schema"></a>Element VSIXLanguagePack (schemat VSIX Language Pack)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Wymagane. Zawiera element główny pakietu językowego VSIX. Pakietu językowego VSIX zawiera informacje dotyczące instalacji zlokalizowanego pakietu VSIX.  
  
## <a name="syntax"></a>Składnia  
  
```  
<VSIXLanguagePack>  
  <LocalizedName>...</LocalizedName>  
  <LocalizedDescription>...</LocalizedDescription>  
  <MoreInfoURL>...</MoreInfoURL>  
  <License>...</License>  
</VSIXLanguagePack>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`xmlns`|Przestrzeń nazw XML, w którym zdefiniowano schematu językowego VSIX.|  
  
## <a name="xmlns-attribute"></a>Atrybut xmlns  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`http://schemas.microsoft.com/developer/vsx-schema-lp/2010`|Wymagane. Lokalizacja pliku, który definiuje schemat pakietów językowych.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[LocalizedName, element](../extensibility/localizedname-element-vsix-language-pack-schema.md)|Wymagane. Zlokalizowana nazwa rozszerzenia do zainstalowania.|  
|[LocalizedDescription, element](../extensibility/localizeddescription-element-vsix-language-pack-schema.md)|Wymagane. Zlokalizowany opis rozszerzenia do zainstalowania.|  
|[MoreInfoURL, element](../extensibility/moreinfourl-element-vsix-language-pack-schema.md)|Opcjonalna. Łącze do zlokalizowanych informacji o rozszerzeniu.|  
|[License, element](../extensibility/license-element-vsix-language-pack-schema.md)|Opcjonalna. Ścieżka zlokalizowaną wersję pliku licencji dla rozszerzenia.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|Brak||  
  
## <a name="element-information"></a>Informacje o elementach  
  
|||  
|-|-|  
|Przestrzeń nazw|http://schemas.microsoft.com/developer/vsx-schema-lp/2010|  
|Nazwa schematu|VSIX Language Pack schematu|  
|Plik walidacji|VSIXLanguagePackSchema.xsd|  
|Może być pusta|Nie|  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do schematu VSX Language Pack](../extensibility/vsx-language-pack-schema-reference.md)   
 [Lokalizowanie pakietów VSIX](../extensibility/localizing-vsix-packages.md)   
 [Odwołanie do schematu 1.0 rozszerzenia VSIX](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)

