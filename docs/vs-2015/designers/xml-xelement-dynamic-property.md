---
title: XML (właściwość dynamiczna XElement) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- XElement.Xml
ms.assetid: 69ab2a33-4fe7-4cfa-97f8-eaf063decb18
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6daf831030fd02f3aa1e3a4844a42ba60bf0574c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49175815"
---
# <a name="xml-xelement-dynamic-property"></a>XML (właściwość dynamiczna XElement)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pobiera niesformatowany XML zawartości elementu.  
  
## <a name="syntax"></a>Składnia  
  
```  
elem.Xml  
```  
  
## <a name="property-valuereturn-value"></a>Wartość właściwości/Zwracana wartość  
 A <xref:System.String> reprezentujący niesformatowany zawartość XML elementu.  
  
## <a name="remarks"></a>Uwagi  
 Ta właściwość jest równoważna <xref:System.Xml.Linq.XNode.ToString%28System.Xml.Linq.SaveOptions%29> metody <xref:System.Xml.Linq.XNode?displayProperty=fullName> klasy, za pomocą `SaveOptions` parametr <xref:System.Xml.Linq.SaveOptions>.  
  
## <a name="see-also"></a>Zobacz też  
 [Właściwości dynamiczne klasy XElement](../designers/xelement-class-dynamic-properties.md)   
 [Wartość](../designers/value-xelement-dynamic-property.md)



