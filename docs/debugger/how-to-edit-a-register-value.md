---
title: 'Porady: Edytowanie wartości rejestru | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.register.edit
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Registers window, editing register values
- register values
ms.assetid: e27b6bd8-e6d4-4f1d-8a86-9f4047bb1167
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de743aa67b3875654dee1b13b27a74e208bb6d53
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
ms.locfileid: "31475006"
---
# <a name="how-to-edit-a-register-value"></a>Porady: edytowanie wartości rejestru
Okno rejestrów jest dostępna tylko wtedy, gdy debugowanie poziomie adresu jest włączone w **opcje** okno dialogowe **debugowanie** węzła.  
  
### <a name="to-change-the-value-of-a-register"></a>Aby zmienić wartość rejestru  
  
1.  W **rejestruje** okna, użyj klawisza TAB lub mysz, aby przenieść wstawiania wskaż wartość ma zostać zmieniony. Po rozpoczęciu wpisywania kursor musi znajdować się przed wartością, którą chcesz zastąpić.  
  
2.  Wpisz nową wartość.  
  
    > [!CAUTION]
    >  Zmiana wartości rejestru (szczególnie w rejestrach element EIP i EBP) mogą wpływać na wykonywanie programów.  
  
    > [!CAUTION]
    >  Edytowanie wartości zmiennoprzecinkowych może spowodować pomocnicza nieścisłości z powodu konwersji decimal-binary ułamkowych składników. Nawet pozornie nieszkodliwe edycji może spowodować zmianę niektórych najmniej znaczących bitów w rejestrze zmiennoprzecinkowych.  
  
## <a name="see-also"></a>Zobacz też  
 [Porady: Korzystanie z okna rejestrów](../debugger/how-to-use-the-registers-window.md)