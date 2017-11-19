---
title: "Zainstaluj na o niskiej przepustowości lub zawodnych w środowiskach sieci | Dokumentacja firmy Microsoft"
description: "W tym artykule opisano, jak Instalator programu Visual Studio działa w warunkach zawodnej sieci i wyjaśniono, jak pobrać pliki instalacji przed rozpoczęciem instalacji."
ms.date: 08/30/2017
ms.reviewer: tims
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 44DB1998-68CD-4560-870A-EE5B993DCF6E
author: timsneath
ms.author: tims
manager: ghogen
ms.openlocfilehash: 57665c39c875b57a1e90c4f57de68f069823cc86
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2017
---
# <a name="install-visual-studio-2017-on-low-bandwidth-or-unreliable-network-environments"></a>Zainstaluj program Visual Studio 2017 na o niskiej przepustowości lub zawodnych w środowiskach sieci

Zalecamy wypróbowanie Instalator sieci web programu Visual Studio&mdash;naszym zdaniem znajdziesz ją dobrej doświadczenie w większości sytuacji.

 > [!div class="button"]
 > [Pobierz program Visual Studio 2017 r.](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)
<br/>

Jednak jeśli połączenie z Internetem jest niedostępne lub zawodnych, można użyć wiersza polecenia utworzyć lokalnej pamięci podręcznej plików trzeba wykonać instalację w trybie offline. Poniżej przedstawiono sposób.

> [!NOTE]
> Jeśli jesteś administratorem przedsiębiorstwa, który chce wykonać wdrożenie programu Visual Studio 2017 klienckich stacjach roboczych, które są zaporą z siecią Internet, zobacz nasze [Tworzenie instalacji sieciowej programu Visual Studio 2017](../install/create-a-network-installation-of-visual-studio.md) i [Uwagi dotyczące instalowania programu Visual Studio w środowisku offline](../install/install-visual-studio-in-offline-environment.md) stron.

## <a name="step-1---download-the-visual-studio-bootstrapper"></a>Krok 1 — pobieranie inicjujący Instalatora programu Visual Studio

Rozpocznij od pobierania programu Visual Studio inicjującego używanej wybranej wersji programu Visual Studio.

Plik Instalatora&mdash;lub dokładniej, plik inicjujący&mdash;będzie odpowiadać lub są podobne do jednej z następujących czynności.

| Wersja                    | Plik                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio Community    | [vs_community.exe](https://aka.ms/vs/15/release/vs_community.exe)       |
| Visual Studio Professional | [vs_professional.exe](https://aka.ms/vs/15/release/vs_professional.exe) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://aka.ms/vs/15/release/vs_enterprise.exe)     |

## <a name="step-2---create-a-local-install-cache"></a>Krok 2 — Tworzenie instalacji lokalnej pamięci podręcznej

Musi mieć połączenie internetowe, aby ukończyć ten krok. Aby utworzyć lokalnego układu, otwórz wiersz polecenia i użyj jednej z poniższych przykładach poleceń: tutaj przykładów założono, że używasz wersji społeczności programu Visual Studio; Dostosuj polecenia odpowiednie dla posiadanej wersji.

- Dla sieci web .NET i .NET — rozwój pulpitu Uruchom polecenie:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

- .NET desktop i Office development Uruchom polecenie:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US```

- Do tworzenia klasycznych aplikacji C++ Uruchom polecenie:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US```

- Aby utworzyć pełną układ lokalnego z wszystkimi funkcjami (będzie to zająć dużo czasu&mdash;mamy _partii_ funkcji!), uruchom:

   ```vs_community.exe --layout c:\vs2017layout --lang en-US```

Jeśli chcesz zainstalować języka innego niż angielski, należy zmienić `en-US` ustawienia regionalne z listy w dolnej części strony. Użyj tej [listy składników i obciążeń dostępne](workload-and-component-ids.md) dostosować pamięć podręczną instalacji, w razie potrzeby.

> [!IMPORTANT]
> Pełny układ Visual Studio 2017 wymaga co najmniej 35 GB miejsca na dysku i może zająć trochę czasu, aby pobrać. Zobacz [używania parametrów wiersza polecenia do zainstalowania programu Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md) informacji na temat sposobu tworzenia układu z tylko składniki do zainstalowania.

## <a name="step-3---install-visual-studio-from-the-local-cache"></a>Krok 3 — Instalacja programu Visual Studio z lokalnej pamięci podręcznej

> [!TIP]
> Po uruchomieniu z instalacji lokalnej pamięci podręcznej, Instalator używa lokalnych wersji każdy z tych plików. Jednak jeśli zostanie wybrana podczas instalacji składników, które nie znajdują się w pamięci podręcznej, możemy próbą pobrania ich z Internetu.

Aby zainstalować tylko pliki, które zostały pobrane, należy użyć tych samych opcji wiersza polecenia używane do tworzenia układu pamięci podręcznej. Na przykład, układu pamięci podręcznej został utworzony przy użyciu następującego polecenia:

```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

Uruchom instalację za pomocą tego polecenia:

```c:\vs2017layout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional```

  > [!NOTE]
  > Jeśli zostanie wyświetlony błąd, że podpis jest nieprawidłowy, należy zainstalować certyfikaty zaktualizowane. Otwórz folder certyfikaty w pamięci podręcznej w trybie offline. Kliknij dwukrotnie plik certyfikatu, a następnie kliknij za pomocą Kreatora Menedżera certyfikatów. Jeśli pojawi się monit o podanie hasła, pozostaw to pole puste.

## <a name="list-of-language-locales"></a>Lista ustawień regionalnych języka

| **Ustawienia regionalne języka** | **Język** |
| ----------------------- | --------------- |
| cs-CZ | czeski |
| de-DE | niemiecki |
| EN US | angielski |
| es-ES | Hiszpański |
| fr-FR | Francuski |
| IT-IT | Włoski |
| ja-JP | japoński |
| ko-KR | koreański |
| pl-PL | polski |
| pt-BR | Portugalski (Brazylia) |
| ru-RU | Rosyjski |
| tr-TR | turecki |
| zh-CN | Chiński (uproszczony) |
| zh-TW. | Chiński — tradycyjny |

## <a name="get-support"></a>Uzyskaj pomoc techniczną
Czasami może wystąpienia problemów. W przypadku niepowodzenia instalacji programu Visual Studio, zobacz [problemy dotyczące instalacji i uaktualniania Rozwiązywanie problemów z programu Visual Studio 2017](troubleshooting-installation-issues.md) stronę porady dotyczące rozwiązywania problemów. Jak również zgłosić problemy produktu z nami za pośrednictwem [zgłosić Problem](../ide/how-to-report-a-problem-with-visual-studio-2017.md) narzędzia w programie Visual Studio IDE lub udział sugestia z nami na [UserVoice](https://visualstudio.uservoice.com/forums/121579). Można śledzić problemy z produktu w [Visual Studio Developer Community](https://developercommunity.visualstudio.com/), zadawać pytania i odpowiedzi. Można również kontaktowaniu się z nami i innymi deweloperami Visual Studio za pomocą naszych [konwersacji programu Visual Studio w społeczności Gitter](https://gitter.im/Microsoft/VisualStudio) (wymaga [GitHub](https://github.com/) konta).

## <a name="see-also"></a>Zobacz także
* [Zainstaluj program Visual Studio](install-visual-studio.md)
* [Przewodnik administratora w usłudze Visual Studio](visual-studio-administrator-guide.md)
* [Korzystanie z parametrów wiersza polecenia do zainstalowania programu Visual Studio](use-command-line-parameters-to-install-visual-studio.md)