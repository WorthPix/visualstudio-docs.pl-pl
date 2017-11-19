---
title: VSPerfCmd | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance tools, VSPerfCmd tool
- command-line tools, VSPerfCmd tool
- command line, tools
- profiling tools,VSPerfCmd
- VSPerfCmd tool
ms.assetid: 778bc105-7643-46c4-a338-f3620e31125a
caps.latest.revision: "49"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 82fada9e9b043511fe94cab6cae99ee9e521f84b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="vsperfcmd"></a>VSPerfCmd
**VSPerfCmd.exe** narzędzie jest używane do uruchamiania i zatrzymywania gromadzenia danych wydajności. Używa następującej składni:  
  
```  
VSPerfCmd [/U] [/options]  
```  
  
 W poniższych tabelach opisano **VSPerfCmd.exe** narzędzia Opcje.  
  
|Opcja|Opis|  
|------------|-----------------|  
|**U**|Konsola przekierowane dane wyjściowe są zapisywane jako Unicode. Musi być pierwszą opcję określony.|  
|[Uruchom](../profiling/start.md) **:**`mode`|Uruchamia usługę profilowania w określonym trybie.|  
|[Dane wyjściowe](../profiling/output.md) **:**`filename`|Określa nazwę pliku wyjściowego. Należy użyć tylko z **Start**.|  
|[CrossSession &#124; CS](../profiling/crosssession.md)|Włącza profilowanie między sesjami systemu Windows. Należy użyć tylko z **Start**, **dołączyć**, **lub uruchom**.|  
|[Użytkownik](../profiling/user-vsperfcmd.md) **:**[`domain\`]`username`|Umożliwia dostęp do określonego konta usługi profilera. Należy użyć tylko z **Start**.|  
|[WaitStart](../profiling/waitstart.md)[**:**`n`]|Czeka na zainicjować rejestratora zbierania danych. Jeśli `n` jest określony, **VSPerfCmd** będzie czekać co najwyżej `n` sekund. Jeśli `n` nie zostanie określony, **VSPerfCmd** będzie czekać w nieskończoność. Ułatwia to użycie **VSPerfCmd** w ramach procesu wsadowego.|  
|[Licznik](../profiling/counter.md) **:**`cfg`|W przypadku przykładowej metoda profilowania określa licznika Procesora i liczba zdarzeń do użycia jako interwał próbkowania. Można przykładowe tylko jedna wartość licznika.<br /><br /> Gdy jest używana metoda profilowania instrumentacji, określa licznika Procesora, które będą zbierane w każdym punkcie instrumentacji. Należy użyć tylko z **Start:**`Trace`, **dołączyć**, lub **uruchamianie**.|  
|[QueryCounters](../profiling/querycounters.md)|Wyświetla listę prawidłowych liczników CPU dla bieżącego komputera.|  
|[WinCounter](../profiling/wincounter.md) **:** *ścieżki*|Określa zdarzenia licznika wydajności systemu Windows zawierający dane znacznik profilu. Należy użyć tylko z **Start**.|  
|[AutoMark](../profiling/automark.md) **:***n*|Określa interwał (w milisekundach) między zdarzenia zbierania danych licznika wydajności systemu Windows. Za pomocą **WinCounter**.|  
|[Zdarzenia](../profiling/events-vsperfcmd.md) **:**`option`|Kolekcja formantów określone zdarzenia funkcji Śledzenie zdarzeń systemu Windows (). Do pliku .itl, który nie jest plik danych (Vsp) profilowania zbierane są dane funkcji ETW.|  
|[Stan](../profiling/status.md)|Wyświetla stan profilera, informacje dotyczące procesów, które są aktualnie PROFILOWANEGO i konta, które mają uprawnienia do kontrolowania profilera.|  
|[Zamknięcie](../profiling/shutdown.md)[**:**`n`]|Zamyka plik danych profilowania i wyłącza profilera.|  
|[GlobalOn](../profiling/globalon-and-globaloff.md)|Wznawia zbieranie danych po wywołaniu **VSPerfCmdGlobalOff**.|  
|[GlobalOff](../profiling/globalon-and-globaloff.md)|Zatrzymuje wszystkie zbierania danych, ale nie kończy się sesja profilowania.|  
|[ProcessOn](../profiling/processon-and-processoff.md) **:**`pid`|Wznawia zbierania danych dla określonego procesu po profilowania została wstrzymana przez wywołanie do **VSPerfCmdProcessOff**.|  
|[ProcessOff](../profiling/processon-and-processoff.md) **:**`pid`|Zatrzymuje zbieranie danych dla określonego procesu.|  
|[ThreadOn i ThreadOff](../profiling/threadon-and-threadoff.md) **:** *tid*|Wznawia profilowania określony proces po profilowania została wstrzymana przez wywołanie do **VSPerfCmdThreadOff**. Użyj **ThreadOn** tylko wtedy, gdy profilowania przy użyciu metody instrumentacji.|  
|[ThreadOn i ThreadOff](../profiling/threadon-and-threadoff.md) **:** *tid*|Zatrzymuje profilowanie dla określonego wątku. Użyj **ThreadOff** tylko wtedy, gdy profilowania przy użyciu metody instrumentacji.|  
|[Oznacz](../profiling/mark.md) **:** *Nr_znacznika*[**,***Tekst_znacznika***]**|Wstawia znacznik do pliku danych profilowania, tekstem opcjonalne.|  
  
## <a name="sampling-method-options"></a>Opcje metody pobierania próbek  
 Poniższe opcje są dostępne tylko w przypadku, gdy używana jest metoda profilowania próbkowania.  
  
|Opcja|Opis|  
|------------|-----------------|  
|[Uruchom](../profiling/launch.md) **:** *pliku wykonywalnego*|Uruchamia określony aplikację i rozpocznie się profilowania.|  
|[Argumenty](../profiling/args.md) **:** *argumentów*|Określa argumenty wiersza polecenia do przekazania do uruchomionej aplikacji.|  
|[Konsoli](../profiling/console.md)|Uruchamia określone polecenie nowe okno wiersza polecenia.|  
|[Dołącz](../profiling/attach.md) **:** *PID*[**,***PID*]|Rozpoczyna się profilowania określonych procesów. Procesy można zidentyfikować według identyfikatora procesu lub nazwy procesu.|  
|[Odłącz](../profiling/detach.md)[**:***PID*[,*PID*]]|Zatrzymuje profilowanie określonych procesów. Procesy można zidentyfikować według identyfikatora procesu lub nazwy procesu. Jeśli żaden proces nie zostanie określony, Profilowanie jest zostało zatrzymane dla wszystkich procesów.|  
|[Wykaz Globalny](../profiling/gc-vsperfcmd.md)[**:**{**alokacji**`&#124;`**okres istnienia**}]|Umożliwia zbieranie danych pamięci .NET alokacji i obiekt okres istnienia. Należy użyć tylko z **VSPerfCmdLaunch** opcji.|  
  
### <a name="sampling-interval-options"></a>Opcje interwał próbkowania  
 Poniższe opcje, określ typ i czas trwania interwałów próbkowania. Wartość domyślna to **czasomierza**. Można również określić licznika Procesora jako interwał, używając **licznika** opcji. Te opcje można określić tylko w przypadku **uruchamianie** lub przy pierwszym **Attach** sesji profilowania.  
  
|Opcja|Opis|  
|------------|-----------------|  
|[PF](../profiling/pf.md)[**:***n*]|Próbki na każdym błąd strony n-ty percentyl (domyślne = 10).|  
|[Sys](../profiling/sys-vsperfcmd.md)[**:***n*]|Przykłady przy każdym wywołaniu systemie n-ty percentyl (domyślne = 10).|  
|[Czasomierz](../profiling/timer.md)[**:***n*]|Cykl próbki na każdym n-ty percentyl procesora (domyślne = 10000000).|  
  
## <a name="service-component-and-kernel-mode-device-options"></a>Składnik usługi i opcje urządzenia trybu jądra  
 Następujące opcje Admin obsługuje składniki usługi profilowania lub sterowniki urządzenia trybu jądra. Opcje administratora Ustawianie uprawnień profilowania i kontrolować PROFILOWANEGO usługi lub sterownika urządzenia.  
  
 Opcje administratora musi zostać wykonana w wierszu polecenia, który działa z poświadczeniami administracyjnymi.  
  
|Opcja|Opis|  
|------------|-----------------|  
|**Admin** \< **Zezwalaj &#124; ODMÓW**> *prawej*[ *prawej*] \< *użytkownika* &#124; *Grupy*>|Zezwala lub nie zezwala określonemu użytkownikowi lub grupie dostępu do usługi profilowania.<br /><br /> `Right`można:<br /><br /> CrossSession — zapewnia dostęp użytkownika do usługi przetnie sesji profilowania.<br /><br /> SampleProfiling — daje użytkownikowi dostęp do sterownika, aby włączyć profilowanie próbkowania. Umożliwia również dostęp do informacji o przejście jądra podczas profilowania śledzenia.<br /><br /> FullAccess — zapewnia dostęp zarówno CrossSession, jak i SampleProfiling.|  
|**Admin, lista**|Wyświetla listę bieżącego stanu usług profilowania i wyświetla listę uprawnień użytkownika.|  
|**Administrator:** \< *usługi*&#124; *Sterownik*>\<**START**&#124; **Zatrzymaj**&#124; **Zainstaluj**&#124; **ODINSTALUJ**>|Uruchamia, zatrzymuje, instaluje lub odinstalowuje składnik usługi profilowania (usługa) lub sterownik urządzenia trybu jądra (driver).|  
|**Administrator:** \< *usługi*&#124; *Sterownik*>**AutoStart**\<**ON**&#124; **WYŁĄCZANIE**>|Włącza lub wyłącza automatyczne uruchamianie usługi profilowania (usługa) lub sterownik urządzenia trybu jądra (driver) po ponownym uruchomieniu.|  
  
## <a name="vsperfcmd-driver"></a>/ Driver narzędzia VSPerfCmd  
 **/Driver narzędzia VSPerfCmd** jest teraz przestarzałe. Użyj **VsPerfCmdAdmin** opcje dla tej funkcji.  
  
## <a name="see-also"></a>Zobacz też  
 [Narzędzie VSInstr](../profiling/vsinstr.md)   
 [Vsperfmon —](../profiling/vsperfmon.md)   
 [VSPerfReport](../profiling/vsperfreport.md)