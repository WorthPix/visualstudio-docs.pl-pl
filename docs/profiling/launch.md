---
title: Uruchamianie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: f81bde5c-3394-4b79-a315-c2f6491689b3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3b34cf3124ab4479be624f097502240e5014b330
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844407"
---
# <a name="launch"></a>Uruchom
**Uruchamianie** opcja uruchamiania przy użyciu metody próbkowania profilera i rozpoczyna się również określonej aplikacji.  
  
 Do używania **uruchamianie** opcji, należy określić **próbki** metody w **Start** opcji.  
  
## <a name="syntax"></a>Składnia  
  
```cmd  
VSPerfCmd.exe /Launch:AppName [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `AppName`  
 Nazwa aplikacji do uruchomienia. Obsługiwane są pełne i częściowe ścieżki z bieżącego katalogu.  
  
## <a name="valid-options"></a>Prawidłowe opcje  
 Następujące opcje narzędzia VSPerfCmd można łączyć z **uruchamianie** opcji w jednym wierszu polecenia.  
  
 **Uruchom:** `Method`  
 Inicjuje sesję wiersza polecenia profilera i ustawia określonej metody profilowania.  
  
 **GlobalOn**i **GlobalOff**  
 Wznawia (**GlobalOn**) lub wstrzymuje (**GlobalOff**) profilowania, ale nie kończy się sesja profilowania.  
  
 **ProcessOn:** `PID` i **ProcessOff**:`PID`  
 Wznawia (**ProcessOn**) lub wstrzymuje (**ProcessOff**) profilowania dla określonego procesu.  
  
 **TargetCLR**  
 Określa wersję programu .NET Framework wspólnego języka środowiska uruchomieniowego (CLR) do profilu, gdy więcej niż jedna wersja jest ładowany w sesji profilowania. Domyślnie jest profilowane pierwszy załadowano wersję.  
  
## <a name="exclusive-options"></a>Wykluczających się opcji  
 Następujące opcje można używać tylko z **uruchamianie** opcji.  
  
 **Console**  
 Uruchamia określony aplikacji wiersza polecenia w nowym oknie.  
  
 **Argumenty:** `ArgList`  
 Określa listę argumenty do przekazania do aplikacji.  
  
 **LineOff**  
 Wyłącza funkcję zbierania danych profilowania na poziomie wiersza.  
  
## <a name="sampling-options"></a>Opcje pobierania próbek  
 Można określić jedną z następujących opcji Interwał próbkowania na **uruchamianie** wiersza polecenia. Domyślny interwał próbkowania wynosi 10 000 000 cykli zegara procesora.  
  
 **Czasomierz**[**:**`Cycles`]**PF**[**:**`Events`]**Sys**[**:**`Events`] **Licznik**[**:**`Name`,`Reload`,`FriendlyName`]**GC**[:**alokacji** &#124;  **okres istnienia**]  
 Określa liczbę i typ interwału próbkowania.  
  
-   **Czasomierz** — przykłady co `Cycles` cykle zegara procesora nie zostało zatrzymane. Jeśli `Cycles` nie zostanie określony, 10 000 000 cykle są używane.  
  
-   **PF** — przykłady co `Events` błędów stron. Jeśli `Events` nie zostanie określony, 10 błędów stron.  
  
-   **Sys** — przykłady co `Events` wywołań do systemu operacyjnego. Jeśli `Events` nie zostanie określony, 10 wywołań systemowych są używane.  
  
-   **Licznik** — przykłady co `Reload` liczba wydajności procesora CPU licznika określony przez `Name`. Opcjonalnie `FriendlyName` można określić ciąg do użycia w nagłówku kolumny raportów profilera.  
  
-   **Wykaz Globalny** -.NET umożliwia zbieranie danych pamięci. Domyślnie (**alokacji**), dane są zbierane w każdym zdarzeniu alokacji pamięci. Gdy **okres istnienia** parametr jest określony, również zbieranych danych w każdym zdarzeniu kolekcji pamięci.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie przedstawiono użycie **uruchamianie** do uruchomienia aplikacji.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Zobacz także  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profil aplikacji autonomicznych](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Aplikacje sieci web ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Usługi profilowania](../profiling/command-line-profiling-of-services.md)