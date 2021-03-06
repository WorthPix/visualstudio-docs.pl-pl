---
title: 'Porady: zastosowanie edytowania w trybie przerwania z opcją Edytuj i Kontynuuj | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [Visual Basic], applying edits in break mode
- break mode, applying code changes
- Edit and Continue, applying edits in break mode
- editing, break mode
- coding, editing in break mode
- code, editing in break mode
ms.assetid: 1eef7498-6a1f-4fba-8146-510adc6375c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f031598e0c8f290907e759bcfceac85c1b063f5f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
ms.locfileid: "31474196"
---
# <a name="how-to-apply-edits-in-break-mode-with-edit-and-continue"></a>Porady: stosowanie edycji w trybie przerwania za pomocą pleceń Edytuj i Kontynuuj
Edytuj i Kontynuuj służy do edytowania kodu w trybie przerwania, a następnie kontynuuj bez zatrzymywanie i ponowne uruchamianie wykonywania.  
  
Ograniczenia dotyczące używania podczas debugowania Edytuj i Kontynuuj, zobacz [obsługiwane zmiany kodu (C# i Visual Basic](../debugger/supported-code-changes-csharp.md)]
  
### <a name="to-edit-code-in-break-mode"></a>Aby zmodyfikować kod w trybie przerwania  
  
1.  Tryb przerwania, wykonując jedną z następujących czynności:  
  
    -   Ustaw punkt przerwania w kodzie, a następnie wybierz pozycję **Rozpocznij debugowanie** z **debugowania** menu i poczekaj aplikacji trafienie punktu przerwania.  
  
         —lub—  
  
    -   Rozpocznij debugowanie, a następnie wybierz **Przerwij wszystkie** z **debugowania** menu.  
  
         —lub—  
  
    -   Po wystąpieniu wyjątku, wybierz **Włącz edytowanie** na**Asystenta wyjątków**.  
  
2.  Zmiany kodu żądaną i obsługiwane.  
  
     Aby uzyskać więcej informacji, zobacz [obsługiwane zmiany kodu (C# i Visual Basic](../debugger/supported-code-changes-csharp.md).  
  
    > [!NOTE]
    >  Jeśli podjęto Aby zmienić kod nie jest dozwolona przez Edytuj i Kontynuuj, edycji zostanie podkreślone linią faliste purpurowa i zadanie zostanie wyświetlone na liście zadań. Nie można kontynuować wykonywanie kodu, o ile nie można cofnąć tej zmiany niedozwolony kod.  
  
3.  Na **debugowania** menu, kliknij przycisk **Kontynuuj** można wznowić wykonywania.  
  
     Kod wykonuje obecnie zastosowanej edycji włączona do projektu.  
  
## <a name="see-also"></a>Zobacz też  
 [Obsługiwane zmiany kodu (C# i Visual Basic](../debugger/supported-code-changes-csharp.md)   
 [Edytuj i kontynuuj (Visual Basic)](../debugger/edit-and-continue-visual-basic.md)