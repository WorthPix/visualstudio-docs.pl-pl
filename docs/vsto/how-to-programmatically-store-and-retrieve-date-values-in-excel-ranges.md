---
title: "Porady: programowane przechowywanie i pobieranie wartości daty w zakresach Excel | Dokumentacja firmy Microsoft"
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
- Excel [Office development in Visual Studio], retrieving date values from ranges
- ranges, retrieving data values
- dates, retrieving from Excel ranges
- Excel [Office development in Visual Studio], storing date values in ranges
- date values, storing in Excel ranges
- dates, storing in Excel ranges
- ranges, storing date values
- date values
ms.assetid: e1cdd262-0356-4499-8bc5-e730f74235a2
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4d19de6848da22238dc1cf394fa3d417ea0d8c88
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-store-and-retrieve-date-values-in-excel-ranges"></a>Porady: Programowane przechowywanie i pobieranie wartości daty w zakresach programu Excel
  Umożliwia przechowywanie i pobieranie wartości w <xref:Microsoft.Office.Tools.Excel.NamedRange> formant lub obiekt zakresu natywnego programu Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Przechowywanie wartości daty, która znajduje się na lub po 1/1/1900 w zakresie za pomocą narzędzi programowania pakietu Office w Visual Studio, jest on przechowywany w formacie OLE automatyzacji (OA). Należy użyć <xref:System.DateTime.FromOADate%2A> metody do pobierania wartości daty OLE automatyzacji (OA). Data jest wcześniejsza niż 1/1/1900, jest on przechowywany jako ciąg.  
  
> [!NOTE]  
>  Excel dat różnią się od daty automatyzacji OLE na pierwszych dwóch miesięcy 1900 roku. Istnieją także różnice Jeśli **system daty 1904** zaznaczenia pola wyboru. Poniższe przykłady kodu nie dotyczą te różnice.  
  
## <a name="using-a-namedrange-control"></a>Używanie formantu NamedRange  
  
-   W tym przykładzie jest na poziomie dokumentu. Poniższy kod muszą znajdować się w klasie arkusza nie znajduje się w `ThisWorkbook` klasy.  
  
#### <a name="to-store-a-date-value-in-a-named-range"></a>Przechowywanie wartości daty nazwanego zakresu  
  
1.  Utwórz <xref:Microsoft.Office.Tools.Excel.NamedRange> formant w komórce **A1**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#50](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#50)]
     [!code-vb[Trin_VstcoreExcelAutomation#50](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#50)]  
  
2.  Ustaw bieżącą datę jako wartość `NamedRange1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#51](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#51)]
     [!code-vb[Trin_VstcoreExcelAutomation#51](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#51)]  
  
#### <a name="to-retrieve-a-date-value-from-a-named-range"></a>Aby pobrać wartość daty z nazwanego zakresu  
  
1.  Pobieranie wartości daty z `NamedRange1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#52](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#52)]
     [!code-vb[Trin_VstcoreExcelAutomation#52](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#52)]  
  
## <a name="using-native-excel-ranges"></a>Za pomocą natywnego zakresów programu Excel  
  
#### <a name="to-store-a-date-value-in-a-native-excel-range-object"></a>Przechowywanie wartości daty w obiekcie range natywnego programu Excel  
  
1.  Utwórz <xref:Microsoft.Office.Interop.Excel.Range> reprezentujący komórki **A1**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#25](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#25](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#25)]  
  
2.  Ustaw bieżącą datę jako wartość `rng`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#26](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#26](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#26)]  
  
#### <a name="to-retrieve-a-date-value-from-a-native-excel-range-object"></a>Aby pobrać wartość daty z natywnego obiektu zakresu programu Excel  
  
1.  Pobieranie wartości daty z `rng`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#27](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#27)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#27](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#27)]  
  
## <a name="see-also"></a>Zobacz też  
 [Praca z zakresami](../vsto/working-with-ranges.md)   
 [Model obiektu Excel ― omówienie](../vsto/excel-object-model-overview.md)   
 [Namedrange — formant](../vsto/namedrange-control.md)   
 [Porady: programowane odwoływanie do zakresów arkusza w kodzie](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Porady: dodawanie formantów NamedRange do arkuszy](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Parametry opcjonalne w rozwiązaniach pakietu Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  