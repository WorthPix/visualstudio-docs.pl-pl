---
title: "Porady: programowane otwieranie plików tekstowych jako skoroszytu | Dokumentacja firmy Microsoft"
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
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
ms.assetid: 056ae3d0-7fe7-4c28-a2a5-5a948baee0e6
caps.latest.revision: "47"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b4148a9a8a8de627ed56f5e1abc6da3469399330
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>Porady: Programowane otwieranie plików tekstowych jako skoroszytu
  Jako skoroszyt, można otworzyć pliku tekstowego. Należy podać nazwę pliku tekstowego, który chcesz otworzyć. Można określić kilka opcjonalnych parametrów, takich jak numer wiersza do analizowania na początku i format kolumny danych w pliku.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="example"></a>Przykład  
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 W tym przykładzie wymaga następujących składników:  
  
-   Plik tekstu rozdzielanego przecinkami o nazwie `Test.txt` zawiera co najmniej trzy wiersze tekstu.  
  
-   Plik tekstowy `Test.txt` do przechowywania na dysku C.  
  
## <a name="see-also"></a>Zobacz też  
 [Praca ze skoroszytami](../vsto/working-with-workbooks.md)   
 [Porady: programowane otwieranie skoroszytów](../vsto/how-to-programmatically-open-workbooks.md)   
 [Porady: programowane tworzenie nowych skoroszytów](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [Porady: programowane zapisywanie skoroszytów](../vsto/how-to-programmatically-save-workbooks.md)   
 [Porady: programowane zamykanie skoroszytów](../vsto/how-to-programmatically-close-workbooks.md)   
 [Parametry opcjonalne w rozwiązaniach pakietu Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  