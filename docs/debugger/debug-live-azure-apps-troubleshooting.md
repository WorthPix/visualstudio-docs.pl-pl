---
title: "Rozwiązywanie problemów i znane problemy dotyczące debugowania migawki | Dokumentacja firmy Microsoft"
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5e111159029710684a1a49be2859f6ac5699a70a
ms.sourcegitcommit: 2c7f48ad6073a81fa927568793633f26cc1f0b15
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2017
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Rozwiązywanie problemów i znane problemy dotyczące migawki debugowania w programie Visual Studio

Jeśli kroki opisane w tym temacie nie rozwiąże problemu, skontaktuj się z snaphelp@microsoft.com.

## <a name="issue-snappoint-does-not-turn-on"></a>Problem: Snappoint jest wyłączone

Jeśli widzisz ikonę ostrzeżenia ![ikona ostrzeżenia Snappoint](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "ikona ostrzeżenia Snappoint") z Twojej snappoint zamiast ikony regularne snappoint następnie snappoint nie jest włączona.

![Nie włączaj Snappoint](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "Snappoint jest wyłączone")

Wykonaj następujące czynności:

1. Upewnij się, że korzystasz z tej samej wersji kodu źródłowego, który był używany do tworzenia i wdrażania aplikacji.
1. Upewnij się, że są ładowane poprawne symbole dla danego wdrożenia. Aby to zrobić, należy wyświetlić **modułów** okno podczas debugowania migawki i sprawdź kolumna pliku symboli zawiera plik PDB dla modułu debugowania. Należy pamiętać, że debuger migawki podejmie próbę automatycznego pobrania i zastosowania symboli dla danego wdrożenia.

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>Problem: Symbole nie są ładowane, podczas otwierania migawki

Jeśli zostanie wyświetlone następujące okno, symbole nie został załadowany.

![Nie ładuj symbole](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "symbole nie są ładowane.")

Wykonaj następujące czynności:

- Kliknij przycisk **zmiany ustawień symboli...** łącze na tej stronie. W **debugowanie > Symbol** ustawienia, Dodaj katalog pamięci podręcznej symboli. Uruchom ponownie debugowanie migawki po ustawieniu ścieżki symboli.

   Symbole lub .pdb, pliki, dostępne w projekcie musi odpowiadać wdrożenia usługi aplikacji. Większości wdrożeń (wdrożenia za pomocą programu Visual Studio, CI/CD programu VSTS lub Kudu, itp.) będą publikowane plików symboli wraz z usługi aplikacji. Ustawianie katalogu pamięci podręcznej symboli umożliwia Visual Studio, aby użyć tych symboli.

   ![Symbol ustawienia](../debugger/media/snapshot-troubleshooting-symbol-settings.png "ustawień symboli")

- Alternatywnie Jeśli Twoja organizacja korzysta z serwera symboli lub porzuca symbole w inną ścieżkę, należy użyć ustawień symbol załadować poprawne symbole dla danego wdrożenia.

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>Problem: nie widzę opcja "Dołącz debugera migawki" w Eksploratorze chmury

Wykonaj następujące czynności:

- Upewnij się, że jest zainstalowany składnik debugera migawki. Otwórz Instalator programu Visual Studio i sprawdź **debugera migawki** składnika pracą platformy Azure.
- Upewnij się, że aplikacja jest obsługiwana. Obecnie tylko ASP.NET (4.6.1+) i aplikacje platformy ASP.NET Core (2.0 +) wdrożone usługi aplikacji Azure są obsługiwane.

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>Problem: można wyświetlić tylko ograniczony migawek w narzędziach diagnostycznych

![Throttled snappoint](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "Zdławionych snappoint")

Wykonaj następujące czynności:

- Migawki potrwać bardzo mała ilość pamięci, ale ma opłat zatwierdzania. Jeśli debuger migawki wykrywa, że serwer jest pamięci mocno obciążony, nie będą brane migawki. Można usunąć migawki już przechwyconych zatrzymywania sesji debugera migawki i podjęcie ponownej próby.

## <a name="known-issues"></a>Znane problemy

- Migawki debugowania z wielu klientów programu Visual Studio z tej samej usługi aplikacji nie jest obecnie obsługiwane.
- Optymalizacje Roslyn IL nie są w pełni obsługiwane w projektów platformy ASP.NET Core. Dla niektórych projektów platformy ASP.NET Core mogą nie być mogli zobaczyć niektóre zmienne ani niektóre zmienne w instrukcjach warunkowego. 
- Zmienne specjalne, takie jak *$FUNCTION* lub *$CALLER*, nie można obliczyć w instrukcji warunkowej lub logpoints dla projektów platformy ASP.NET Core.
- Debugowanie migawki nie działa na usługi aplikacji, która ma [buforowanie lokalne](https://docs.microsoft.com/en-us/azure/app-service/app-service-local-cache) włączona.

## <a name="see-also"></a>Zobacz także

[Debugowanie w programie Visual Studio](../debugger/index.md)  
[Debugowania na żywo aplikacji ASP.NET, za pomocą debugera migawki](../debugger/debug-live-azure-applications.md)  
[Często zadawane pytania dotyczące debugowania migawki](../debugger/debug-live-azure-apps-faq.md)  