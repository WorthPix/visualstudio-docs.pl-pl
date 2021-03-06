---
title: (Visual Studio SDK) do obsługi wyjątków | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], exception handling
ms.assetid: 7279dc16-db14-482c-86b8-7b3da5a581d2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ab3a3aafdca83305b86ce083e53e654b637cf110
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2018
ms.locfileid: "39232068"
---
# <a name="exception-handling-visual-studio-sdk"></a>Obsługa wyjątków (Visual Studio SDK)
Poniżej opisano proces, który występuje, gdy wyjątki zostaną zgłoszone.  
  
## <a name="exception-handling-process"></a>Proces obsługi wyjątków  
  
1.  Kiedy najpierw jest zgłaszany wyjątek, ale przed zapewniona jest obsługa przez program obsługi wyjątków w programie debugowany, aparat debugowania (DE) wysyła [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) do Menedżer debugowania sesji (SDM) jako zdarzenie zatrzymywania. `IDebugExceptionEvent2` Są wysyłane, jeśli tylko ustawienia, dla wyjątku (określone w oknie dialogowym Wyjątki w pakiecie debugowania) określ, czy użytkownik chce, aby zatrzymać na powiadomienia o wyjątkach pierwszej szansy.  
  
2.  Wywołania SDM [IDebugExceptionEvent2::GetException](../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) pobrać właściwości wyjątku.  
  
3.  Wywołania pakietu debugowania [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) do określenia, jakie opcje do zaprezentowania użytkownikowi.  
  
4.  Debugowanie pakietu pyta użytkownika, jak obsłużyć wyjątek, otwierając okno dialogowe wyjątku pierwszej szansy.  
  
5.  Jeśli użytkownik zdecyduje kontynuować, wywołuje metodę SDM [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md).  
  
    -   Jeśli metoda zwraca wartość S_OK, wywołuje metodę [IDebugExceptionEvent2::PassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-passtodebuggee.md).  
  
         —lub—  
  
         Jeśli metoda zwraca wartość S_FALSE, program debugowany otrzymuje drugą szansę, aby obsłużyć wyjątek.  
  
6.  Jeśli aktualnie debugowanego żadna procedura obsługi wyjątku pierwszej próby na sekundę, DE wysyła `IDebugExceptionEvent2` do SDM jako **EVENT_SYNC_STOP**.  
  
7.  Debugowanie pakietu pyta użytkownika, jak obsłużyć wyjątek, otwierając okno dialogowe wyjątku pierwszej szansy.  
  
8.  Wywołania pakietu debugowania [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) do określenia, jakie opcje do zaprezentowania użytkownikowi.  
  
9. Debugowanie pakietu prosi użytkownika sposób obsługi wyjątku, otwierając okno dialogowe wyjątku szansy na sekundę.  
  
10. Jeśli metoda zwraca wartość S_OK, wywołuje metodę `IDebugExceptionEvent2::PassToDebuggee`.  
  
## <a name="see-also"></a>Zobacz także  
 [Wywoływanie zdarzeń debugera](../../extensibility/debugger/calling-debugger-events.md)