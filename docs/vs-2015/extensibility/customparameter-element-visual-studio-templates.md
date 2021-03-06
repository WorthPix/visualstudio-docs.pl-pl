---
title: CustomParameter, Element (szablony Visual Studio) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#CustomParameter
helpviewer_keywords:
- CustomParameters element [Visual Studio project templates]
ms.assetid: 743c4489-74ac-403a-bbaa-eed7d785a3ac
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9540b42497b15eace2ed7a54ef9c26f76c0576a6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49198851"
---
# <a name="customparameter-element-visual-studio-templates"></a>CustomParameter — Element (szablony Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zawiera nazwę niestandardowego parametru i wartości do użycia podczas projektu lub elementu jest tworzone na podstawie szablonu.  
  
## <a name="syntax"></a>Składnia  
  
```  
<CustomParameter Name="name" Value="value">  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`Name`|Wymagane. Nazwa parametru. Format parametrów jest $*nazwa*$.|  
|`Value`|Wymagane. Wartość zastąpienia dla parametru.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[Customparameters —](../extensibility/customparameters-element-visual-studio-templates.md)|Grupy niestandardowe parametry, które mają być przekazane do Kreatora szablonów, gdy Kreator przeprowadza zamiany parametru.|  
  
## <a name="remarks"></a>Uwagi  
 Gdy szablon zawiera `CustomParameter` elementy, każde wystąpienie `Name` atrybutu zostaje zastąpiona opcją `Value` atrybutu w utworzone pliki projektu lub elementu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak korzystać z kilku niestandardowych parametrów w szablonie. Podczas tworzenia projektu lub elementu za pomocą następujących parametrów niestandardowych, wszystkie wystąpienia szablonu `$color1$` i `$color2$` w szablonie zostanie zastąpiona pliki `Red` i `Blue`, odpowiednio.  
  
```  
<CustomParameters>  
    <CustomParameter Name="$color1$" Value="Red"/>  
    <CustomParameter Name="$color2$" Value="Blue "/>  
</CustomParameters>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Customparameters — Element (szablony Visual Studio)](../extensibility/customparameters-element-visual-studio-templates.md)   
 [Parametry szablonu](../ide/template-parameters.md)   
 [Odwołanie do schematu szablonu Visual Studio](../extensibility/visual-studio-template-schema-reference.md)

