---
title: "Właściwości w projektach pakietu Office | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Trust Assemblies Location property
- Cache in Document property
- properties [Office development in Visual Studio]
- Namespace for Host Item property
- Office projects [Office development in Visual Studio], properties
- projects [Office development in Visual Studio], properties
- Value2 property
ms.assetid: 1284d6c3-8200-4151-88ce-0b5c7765af25
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8c5832388db7e70791193024b263da275cdf5eaa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="properties-in-office-projects"></a>Właściwości w projektach pakietu Office
  Istnieje kilka ważnych właściwości, które są dostępne dla projektów pakietu Office w Visual Studio. Te właściwości można uzyskać w **właściwości** okna.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="namespace-for-host-item"></a>Namespace elementu hosta  
 Użyj **Namespace elementu hosta** właściwości do zmiany przestrzeni nazw dla klas elementu hosta (na przykład `ThisAddIn`, `ThisWorkbook`, lub `ThisDocument` klasy) w projektach Visual C#. Ta właściwość jest wyświetlana w **właściwości** okna po wybraniu węzła dokumentu w projektach na poziomie dokumentu (na przykład ExcelWorkbook1.xlsx lub WordDocument1.docx) lub węzła aplikacji w projekcie dodatku narzędzi VSTO (np. programu Excel lub Word ) w **Eksploratora rozwiązań**.  
  
 Podczas tworzenia projektu Visual C# Office elementy hosta są podane przestrzeni nazw na podstawie nazwy projektu. Zaleca się, że używasz **Namespace elementu hosta** właściwość można zmienić przestrzeni nazw, a nie Edytuj kod, pliki bezpośrednio. Korzystając z tej właściwości, przestrzeń nazw zostanie zmieniona w plikach wygenerowanego kodu (ukryte), a także w plikach widoczne kodu.  
  
## <a name="cacheindocument"></a>CacheInDocument  
 **CacheInDocument** właściwość jest widoczna w **właściwości** okna dla projektów na poziomie dokumentu po wybraniu wystąpienia <xref:System.Data.DataSet> w projektancie programu Visual Studio. Tylko publiczne elementy Członkowskie mogą być buforowane; Upewnij się, że **Modyfikatory** właściwość jest ustawiona na **publicznego** aby pamięci podręcznej <xref:System.Data.DataSet>.  
  
 Ta właściwość ma wartość logiczna:  
  
-   Wybierz **true** buforowania zestawu danych w dokumencie.  
  
-   Wybierz **false** Jeśli nie chcesz, aby zestaw danych w pamięci podręcznej w dokumencie.  
  
 Aby uzyskać informacje o buforowaniu danych, zobacz [buforowane dane w dostosowaniach na poziomie dokumentu](../vsto/cached-data-in-document-level-customizations.md).  
  
## <a name="value2"></a>Wartość2  
 **Wartość2** właściwość jest dostępna tylko dla projektów skoroszytu lub szablon programu Excel. Wygląda na to, w obszarze **powiązania danych** w węźle właściwości **właściwości** okna po wybraniu <xref:Microsoft.Office.Tools.Excel.NamedRange> formantu w Projektancie arkusza.  
  
 Użyj **wartość2** właściwości w **właściwości** okno, aby powiązać <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> właściwość <xref:Microsoft.Office.Tools.Excel.NamedRange> pole w źródle danych.  
  
## <a name="see-also"></a>Zobacz też  
 [Projektowanie i tworzenie rozwiązań pakietu Office](../vsto/designing-and-creating-office-solutions.md)   
 [Przegląd szablonów projektu pakietu Office](../vsto/office-project-templates-overview.md)   
 [Zdarzenia w projektach pakietu Office](../vsto/events-in-office-projects.md)  
  
  