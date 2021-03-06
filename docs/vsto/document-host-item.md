---
title: Element hosta dokumentu
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio]
- documents [Office development in Visual Studio], document host items
- document host items
- Word [Office development in Visual Studio], Word documents
- Word [Office development in Visual Studio]
- Word documents
- host items [Office development in Visual Studio], Document
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 10dabdf0cf2db043a5df1b21f5f780645864ae8c
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/22/2018
ms.locfileid: "34448379"
---
# <a name="document-host-item"></a>Element hosta dokumentu
  <xref:Microsoft.Office.Tools.Word.Document> Element hosta jest typem, rozszerzający <xref:Microsoft.Office.Interop.Word.Document> typu z podstawowego zestawu międzyoperacyjnego dla programu Word. <xref:Microsoft.Office.Tools.Word.Document> Element hosta zawiera wszystkie właściwości, metod i zdarzeń jako <xref:Microsoft.Office.Interop.Word.Document> obiekt, ale także przedstawia dodatkowe zdarzenia i działa jako kontener dla kontrolki hosta i formantów formularzy systemu Windows.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 W projektach na poziomie dokumentu, jest domyślnie <xref:Microsoft.Office.Tools.Word.Document> element hosta, który reprezentuje dokumentu w projekcie. W dodatku VSTO projektów, można wygenerować <xref:Microsoft.Office.Tools.Word.Document> hosta elementów w czasie wykonywania.  
  
## <a name="understand-the-document-host-item-in-document-level-projects"></a>Zrozumienie element hosta dokumentu w projektach na poziomie dokumentu  
 Aby uzyskać dostęp do dokumentu w projekcie, należy użyć `ThisDocument` klasy. Podczas tworzenia projektu poziomie dokumentu programu Visual Studio generuje `ThisDocument` klasy jako łącza komunikacyjnego między Word i kod dostosowania. `ThisDocument` Klasy daje dostęp do elementów członkowskich <xref:Microsoft.Office.Tools.Word.Document> element hosta do wykonywania podstawowych zadań w dostosowaniu, takie jak uruchamianie kodu, gdy dokument jest otwarty lub zamknięty. Klasa umożliwia także dodawanie formantów do dokumentu. Łącząc różne zestawy formantów i pisanie kodu, formanty można powiązać z danymi, zbiera informacje o użytkowniku i odpowiadania na działania użytkownika. Aby uzyskać więcej informacji, zobacz [programowania dostosowań na poziome dokumentu](../vsto/programming-document-level-customizations.md).  
  
 `ThisDocument` Klasa udostępnia lokalizacji, w którym można rozpocząć pisanie kodu w projekcie. Ponieważ klasa zawiera wszystkie właściwości, metod i zdarzeń jako <xref:Microsoft.Office.Interop.Word.Document> obiektu w podstawowego zestawu międzyoperacyjnego dla programu Word, można również użyć `ThisDocument` dostępu do modelu obiektów programu Word. Aby uzyskać więcej informacji, zobacz [Przegląd modelu obiektów programu Word](../vsto/word-object-model-overview.md).  
  
### <a name="limitations-of-the-document-host-item-in-document-level-projects"></a>Ograniczenia element hosta dokumentu w projektach na poziomie dokumentu  
 Projekt poziomie dokumentu może zawierać tylko jeden <xref:Microsoft.Office.Tools.Word.Document> element hosta (to znaczy `ThisDocument` klasy). Nie można dodać nowego <xref:Microsoft.Office.Tools.Word.Document> hosta elementy do projektu w czasie projektowania i nie można utworzyć nowego <xref:Microsoft.Office.Tools.Word.Document> hosta elementów w czasie wykonywania z dostosowywania poziomie dokumentu.  
  
 Jeśli tworzysz nowy dokument programu Word w czasie wykonywania, będzie typu <xref:Microsoft.Office.Interop.Word.Document>. Ponieważ nie jest elementem hosta, nie może zawierać żadnych kontrolki hosta lub formanty formularzy systemu Windows. Aby uzyskać więcej informacji o tworzeniu dokumentów w czasie wykonywania, zobacz [porady: programowane tworzenie nowych dokumentów](../vsto/how-to-programmatically-create-new-documents.md).  
  
## <a name="understand-document-host-items-in-application-level-projects"></a>Zrozumienie obiekty hosta dokumentów w projektach na poziomie aplikacji  
 W dodatku VSTO projektów, można wygenerować <xref:Microsoft.Office.Tools.Word.Document> element hosta w czasie wykonywania dla dowolnego dokumentu, który jest otwarty w programie Word. Można użyć <xref:Microsoft.Office.Tools.Word.Document> element hosta do dodawania formantów do skojarzonego dokumentu lub do obsługi zdarzeń, które nie są dostępne na <xref:Microsoft.Office.Interop.Word.Document> obiektów.  
  
 Aby wygenerować <xref:Microsoft.Office.Tools.Word.Document> element hosta, użyj `GetVstoObject` metody. Aby uzyskać więcej informacji, zobacz [dokumentów rozszerzania programu Word i skoroszytów programu Excel w dodatkach VSTO w czasie wykonywania](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="see-also"></a>Zobacz także  
 [Obiekty hosta i informacje o formantach hosta](../vsto/host-items-and-host-controls-overview.md)   
 [Automatyzowanie programu Word za pomocą obiektów rozszerzonych](../vsto/automating-word-by-using-extended-objects.md)   
 [Przegląd modelu obiektów programu Word](../vsto/word-object-model-overview.md)   
 [Ograniczenia programowe elementów hosta i formantów hosta](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Rozszerzanie dokumentów programu Word i skoroszytów programu Excel w dodatkach VSTO w czasie wykonywania](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)  
  
  