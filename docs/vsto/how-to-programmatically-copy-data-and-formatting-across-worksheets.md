---
title: "Porady: programowane kopiowanie danych i formatowanie między arkuszami | Dokumentacja firmy Microsoft"
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
- worksheets, copying data
- formatting [Office development in Visual Studio]
- data [Office development in Visual Studio], copying across worksheets
- copying data, Office development in Visual Studio
ms.assetid: eed7dbaf-bdb5-4330-ba2e-5f3d50817eca
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 065e9b7dd30e2d91f09a4e23aec1880a50521304
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-copy-data-and-formatting-across-worksheets"></a>Porady: Programowane kopiowanie danych i formatowanie między arkuszami
  Można skopiować danych z zakresu na jeden arkusz do wszystkich arkuszy w skoroszycie za pomocą <xref:Microsoft.Office.Interop.Excel.Worksheets.FillAcrossSheets%2A> metody. Określ zakres, i określa, czy chcesz skopiować dane, formatowanie lub oba.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="example"></a>Przykład  
 [!code-csharp[Trin_VstcoreExcelAutomation#44](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#44)]
 [!code-vb[Trin_VstcoreExcelAutomation#44](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#44)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 W tym przykładzie wymaga zakres o nazwie `rangeData` w arkuszu.  
  
## <a name="see-also"></a>Zobacz też  
 [Praca z arkuszami](../vsto/working-with-worksheets.md)   
 [Porady: programowane Dodawanie nowych arkuszy ze skoroszytami](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [Porady: programowane Zmienianie formatowania w wierszach arkusza zawierających zaznaczone komórki](../vsto/how-to-programmatically-change-formatting-in-worksheet-rows-containing-selected-cells.md)   
 [Parametry opcjonalne w rozwiązaniach pakietu Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  