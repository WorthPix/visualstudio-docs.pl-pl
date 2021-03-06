---
title: Instalowanie narzędzi R
description: Jak zainstalować narzędzia R w Visual Studio 2017 i programu Visual Studio 2015, łącznie z instalacji w trybie offline.
ms.date: 01/24/2018
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 1b5cc415d95377cdca0d44c31ed2c3b84cd11c5c
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/20/2018
ms.locfileid: "36296302"
---
# <a name="how-to-install-r-tools-for-visual-studio"></a>Instalowanie narzędzi R dla programu Visual Studio

W tym artykule:

- [Obsługiwane wersje programu Visual Studio](#supported-versions-of-visual-studio)
- [Zainstaluj RTVS w programie Visual Studio 2017 r.](#installing-rtvs-in-visual-studio-2017)
- [Zainstaluj RTVS w programie Visual Studio 2015](#installing-rtvs-in-visual-studio-2015)
- [Instalacja w trybie offline](#offline-installation-of-visual-studio-and-rtvs)

> [!Note]
> Po zainstalowaniu narzędzi R, może zajść potrzeba Konfigurowanie programu Visual Studio dla układu naukowca zoptymalizowane danych, zgodnie z opisem na [opcje](options-for-r-tools-in-visual-studio.md) artykułu.

## <a name="supported-versions-of-visual-studio"></a>Obsługiwane wersje programu Visual Studio

R narzędzi dla programu Visual Studio (RTVS) jest obsługiwana w systemie Windows z społeczność (bezpłatnie), Professional i w wersji Enterprise obu [programu Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) i [programu Visual Studio 2015 Update 3 (lub nowszej)](http://go.microsoft.com/fwlink/?LinkId=691129) (bezpośrednie Pobierz).

RTVS nie jest obecnie obsługiwana w programie Visual Studio dla komputerów Mac.

Nie można zainstalować RTVS, jeśli masz tylko program Visual Studio Shell dołączonego z produktami, takie jak Visual Studio Test Professional i SQL Server Management Studio. Visual Studio Shell nie zawiera składniki niezbędne dla RTVS.

## <a name="install-rtvs-in-visual-studio-2017"></a>Zainstaluj RTVS w programie Visual Studio 2017 r.

1. Uruchom Instalator programu Visual Studio i wybierz **Modyfikuj** opcji (Aby uzyskać więcej informacji, zobacz [zmodyfikować Visual Studio](../install/modify-visual-studio.md)). Jeśli jeszcze nie masz zainstalowanego programu Visual Studio, zobacz [program Visual Studio](../install/install-visual-studio.md). W systemie Windows 7, upewnij się, że Instalatorem zostało zaktualizowane do wyświetlenia wersji programu Visual Studio 2017 *15,2 kompilacji 26430.12* lub nowszym.

1. Wybierz **nauki dane i aplikacje analitycznych** obciążenia:

    ![Dane nauki i obciążenia aplikacji analityczne w VS2017](media/installation-data-science-workload.png)

1. Ustaw dodatkowe opcje z prawej strony z tą samą nazwą obciążenia. Domyślnie to obciążenie obejmuje F # i obsługi języka Python. Dla języka R, są minimalne wymagania **obsługę języka R**, **Obsługa środowiska uruchomieniowego dla rozwoju R**, i **klienta Microsoft R**.

RTVS jest zainstalowany w: *% ProgramFiles (x86) %\Microsoft Visual Studio\<wersji >\<edition > Common7\IDE\Extensions\Microsoft\R Tools for Visual Studio* gdzie  *\<wersji >* jest zwykle `2017` i  *\<edition >* jest `Community`, `Professional`, lub `Enterprise`.

## <a name="install-rtvs-in-visual-studio-2015"></a>Zainstaluj RTVS w programie Visual Studio 2015

Z programem Visual Studio 2015 musisz zainstalować interpreter języka R i narzędzia R oddzielnie.

### <a name="install-an-r-interpreter"></a>Instalowanie interpretera R

RTVS wymaga 64-bitowej instalacji r wersji 3.2.1 lub nowszego z co najmniej jednego z następujących źródeł:

- [Otwórz program Microsoft R](https://mran.microsoft.com/download/)
- [Microsoft R Client](/machine-learning-server/r-client/what-is-microsoft-r-client)
- [SIECI CRAN R](https://cran.r-project.org/bin/windows/base/)

Otwórz R Microsoft R sieci CRAN zarówno i umożliwiają wielu wersji side-by-side. Klient R firmy Microsoft, jednak obsługuje tylko jedną wersję i zawsze używa najnowszego zainstalowane.

### <a name="install-the-r-tools"></a>Zainstaluj narzędzia R

Pobierz bieżący RTVS dla programu Visual Studio 2015 z [ https://aka.ms/rtvs-current ](https://aka.ms/rtvs-current). RTVS sprawdza odpowiedniej wersji programu Visual Studio i ułatwia instalowanie interpretera R, jeśli jeszcze.

> [!Note]
> Autonomiczny Instalator RTVS działa tylko w przypadku programu Visual Studio 2015 roku. z programu Visual Studio 2017 r, zainstaluj obsługę R za pośrednictwem [obciążenia nauki dane i aplikacje analitycznych](#installing-rtvs-in-visual-studio-2017) zgodnie z wcześniejszym opisem.

RTVS dla programu Visual Studio 2015 jest instalowany w: `%ProgramFiles(x86)%\Microsoft Visual Studio 14\Common7\IDE\Extensions\Microsoft\R Tools for Visual Studio`

## <a name="offline-installation-of-visual-studio-and-rtvs"></a>Instalacja programu Visual Studio i RTVS w trybie offline

Instalacja w trybie offline jest odpowiednia dla komputerów, które nie są połączone z Internetem:

1. Postępuj zgodnie z instrukcjami, aby utworzyć Instalatora w trybie offline dla używanej wersji programu Visual Studio:

    - [Visual Studio 2017](../install/create-an-offline-installation-of-visual-studio.md)
    - [Visual Studio 2015](https://msdn.microsoft.com/library/mt706497.aspx)

1. Dla programu Visual Studio 2015, Pobierz instalatorów RTVS w trybie offline z [ https://aka.ms/rtvs-current-zip ](https://aka.ms/rtvs-current-zip) i [ https://aka.ms/rtvs-remote-zip ](https://aka.ms/rtvs-remote-zip).

1. Instalowanie programu Visual Studio i RTVS z instalatorów w trybie offline.

## <a name="see-also"></a>Zobacz także

- [Wprowadzenie do języka R](getting-started-with-r.md)
- [Narzędzia języka R przykładowych projektach](getting-started-samples.md)
- [Pomoc w narzędziach R](getting-started-help.md)
- [Opcje narzędzia R](options-for-r-tools-in-visual-studio.md)
- [Microsoft Machine Learning serwer (dawniej R)](/machine-learning-server/)