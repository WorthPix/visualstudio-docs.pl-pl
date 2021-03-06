---
title: PF | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: cdc0a094-a986-4629-bd1c-dd5fdca323dc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6c86ce1c828ff3f090ce675aeed03a4911a55544
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258973"
---
# <a name="pf"></a>PF
*VSPerfCmd.exe* **PF** opcja umożliwia ustawienie profilowania zdarzenia, które jest próbkowany błędów stron i opcjonalnie powoduje zmianę liczby błędów stron w interwale próbkowania w domyślnej 10.  
  
> [!NOTE]
>  **PF** nie można użyć w systemach 64-bitowych.  
  
**PF** można używać tylko w wierszu polecenia, który zawiera także **uruchamianie** lub **Attach** opcji.  
  
 Domyślnie zdarzenia próbkowania ma ustawioną wartość cykle zegara procesora nie zostało zatrzymane i interwał próbkowania jest ustawiony na 10 000 000. **Czasomierza**, **PF**, **Sys**, i **licznika** opcje umożliwiają ustawianie interwału zdarzeń i pobierania próbek. **GC** opcja służy do zbierania danych pamięci .NET w każdym zdarzeniu kolekcji alokacji i odzyskiwanie. W wierszu polecenia można określić tylko jeden z tych opcji.  
  
 Zdarzenie próbkowania i interwał próbkowania można ustawić tylko w pierwszym wierszu polecenia, zawierający **uruchamianie** lub **Attach** opcji.  
  
## <a name="syntax"></a>Składnia  
  
```cmd  
VSPerfCmd.exe {/Launch:AppName|/Attach:PID} /PF[:Events] [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Events`  
 Wartość całkowita określająca liczbę zdarzeń błędów strony w interwale próbkowania. Jeśli `Events` nie zostanie określony, interwał jest ustawiony na 10.  
  
## <a name="required-options"></a>Wymagane opcje  
 **PF** można określić tylko w wierszu polecenia, która zawiera jeden z następujących opcji.  
  
 **Uruchom:** `AppName`  
 Uruchamia profilera i aplikacji określonej przez AppName.  
  
 **Dołącz:** `PID`  
 Dołącza określony AppName proces profilera.  
  
## <a name="invalid-options"></a>Nieprawidłowe opcje  
 Nie można określić następujące opcje w wierszu polecenia jako **PF**.  
  
 **Czasomierz**[**:**`Cycles`]  
 Ustawia cykli zdarzenie próbkowania zegara procesora i opcjonalnie ustawia interwał próbkowania `Cycles`. Domyślny interwał czasomierza wynosi 10 000 000.  
  
 **Sys**[**:**`Events`]  
 Ustawia zdarzenie próbkowania wywołań z profilowanego aplikacji jądra systemu operacyjnego (syscalls) i opcjonalnie ustawia interwał próbkowania `Events`. Sys domyślny interwał wynosi 10.  
  
 **Licznik:** `Name`[`,Reload`[`,FriendlyName`]]  
 Ustawia zdarzeń pobierania próbek wydajności procesora CPU licznika określony przez `Name` i ustawia interwał próbkowania `Reload`.  
  
 **Wykaz Globalny**[**:**{**alokacji**&#124;**okres istnienia**}]  
 Umożliwia zbieranie danych pamięci .NET. Domyślnie (**alokacji**), dane są zbierane w każdym zdarzeniu alokacji pamięci. Gdy **okres istnienia** parametr jest określony, również zbieranych danych w każdym zdarzeniu kolekcji pamięci.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie pokazano, jak ustawić profilowania zdarzenie próbkowania błędów strony i ustaw interwał próbkowania 20 błędów stron.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /PF:20  
```  
  
## <a name="see-also"></a>Zobacz także  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profil aplikacji autonomicznych](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Aplikacje sieci web ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Usługi profilowania](../profiling/command-line-profiling-of-services.md)