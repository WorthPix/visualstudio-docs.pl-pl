---
title: 'Błąd: Program Microsoft Visual Studio zdalny Monitor debugowania programu na komputerze zdalnym jest uruchomiony jako inny użytkownik | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- -anyuser option
- anyuser option
- Remote Debugging Monitor
- remote debugging, Remote Debugging Monitor
- msvsmon.exe
ms.assetid: e5b18734-2daf-4c58-b5de-24ae1295703e
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba0c145f94e0d4213cdc859edb3b43710d96d257
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49205754"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-is-running-as-a-different-user"></a>Błąd: Monitor debugera zdalnego Microsoft Visual (MSVSMON.EXE) na komputerze zdalnym pracuje jako inny użytkownik
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Podczas próby przeprowadzać debugowanie zdalne, może pojawić się następujący komunikat o błędzie:  
  
 Microsoft Visual Studio zdalny Monitor debugowania programu na komputerze zdalnym jest uruchomiony jako inny użytkownik.  
  
## <a name="cause"></a>Przyczyna  
 Komunikat jest wyświetlany podczas debugowania w trybie bez uwierzytelnienia i użytkownika, który uruchomił polecenie msvsmon nie jest użytkownik, który jest uruchomiony program Visual Studio.  
  
## <a name="solution"></a>Rozwiązanie  
 Aby uruchomić Monitor zdalnego debugowania (msvsmon.exe) jest najbezpieczniejszy i najlepsze rozwiązania, w ramach tego samego konta użytkownika, co program Visual Studio. Jeśli nie możesz tego zrobić, można uruchomić Monitor zdalnego debugowania w ramach konta z **Zezwalaj dowolnemu użytkownikowi na debugowanie** opcji wybranej w monitorze debugera zdalnego **opcje** okno dialogowe.  
  
> [!CAUTION]
>  Udzielanie innym użytkownikom uprawnień do łączenia się temu możliwości przypadkowe łączenie się problem zdalnej sesji debugowania. Debugowanie w **bez uwierzytelniania** tryb nigdy nie jest bezpieczna i należy używać ostrożnie.  
  
 Aby uzyskać więcej informacji, zobacz [uruchomić Monitor zdalnego debugowania](http://msdn.microsoft.com/library/55b60ce7-834b-4e83-a10e-fe4248260a4c).  
  
## <a name="see-also"></a>Zobacz też  
 [Błędy związane z debugowaniem zdalnym i rozwiązywanie problemów](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Debugowanie zdalne](../debugger/remote-debugging.md)



