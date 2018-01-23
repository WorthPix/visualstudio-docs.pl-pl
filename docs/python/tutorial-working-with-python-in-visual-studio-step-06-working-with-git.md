---
title: "Praca z języka Python w programie Visual Studio, krok 6, Praca z usługą Git | Dokumentacja firmy Microsoft"
description: "Krok 6 podstawowy samouczek do pracy z języka Python w programie Visual Studio, obejmujące funkcje związane z Git programu Visual Studio."
ms.custom: 
ms.date: 01/16/2018
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: ef6b3bddfb90c64872de331c988f10595e179eb8
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/22/2018
---
# <a name="step-6-working-with-git"></a>Krok 6: Praca z usługą Git

**Poprzedni krok: [instalowanie pakietów i zarządzanie środowiskiem Python](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md)**

Program Visual Studio udostępnia bezpośrednia Integracja z lokalnym repozytoria Git oraz te, które znajdują się na usługi, takie jak GitHub i Visual Studio Team Services. Integracja obejmuje klonowanie repozytorium, zatwierdzania zmian i zarządzania gałęzi.

W tym temacie opisano tworzenie lokalnego repozytorium Git do istniejącego projektu. Aby uzyskać wskazówki dotyczące tworzenia projektu ze zdalnego repozytorium Git, zobacz [Szybki Start: Klonuj repozytorium kodu języka Python w programie Visual Studio](quickstart-03-project-from-repository.md).

1. Z projektem Otwórz w programie Visual Studio, takich jak projekt z [poprzedniego kroku](tutorial-working-with-python-in-visual-studio-step-05-installing-packages.md), kliknij prawym przyciskiem myszy rozwiązanie i wybierz **Dodaj rozwiązanie do kontroli źródła**. Program Visual Studio tworzy lokalne repozytorium Git, który zawiera kod Twojego projektu i formantów związanych z Git wyświetla również wyświetlane wzdłuż dolnej części okna programu Visual Studio. Pokaż formanty oczekujących zatwierdzeń, zmiany nazwy repozytorium i oddziału. Umieść kursor nad formantów, aby wyświetlić dodatkowe informacje.

  ![Dodatkowe informacje są wyświetlane po aktywowaniu Git formantu w oknie programu Visual Studio](media/working-with-git-01.png)

1. **Team Explorer** również zostanie wyświetlone okno z różnymi opcjami Git, wybierając nagłówka repozytorium. **Synchronizacji** okienka, co zostało pokazane, udostępnia opcje publikowania w repozytorium zdalnym.

  ![Program Team Explorer w programie Visual Studio po utworzeniu lokalnego repozytorium](media/working-with-git-02.png)

1. Wybierz **zmiany** do przeglądania niezatwierdzone zmiany i zatwierdzić je, jeśli to konieczne.

  ![Program Team Explorer w programie Visual Studio przedstawiający niezatwierdzone zmiany](media/working-with-git-03.png)

1. Wybierz **gałęzie** do badania gałęzie i wykonywanie operacji scalania i rebase:

  ![Program Team Explorer w programie Visual Studio przedstawiający gałęzi](media/working-with-git-04.png)

1. Korzystając z lokalnego repozytorium, zatwierdzone zmiany przejdź bezpośrednio do repozytorium. Jeśli korzystasz z repozytorium zdalnym, wybierz **synchronizacji** wypychanej lokalnego zatwierdzenia.

## <a name="going-deeper"></a>Przechodząc głębiej

Bardziej rozległych samouczek na temat pracy z usługą Git, zobacz [udostępnianie kodu programu Visual Studio 2017 i VSTS Git](/vsts/git/share-your-code-in-git-vs-2017)

## <a name="tutorial-review"></a>Przejrzyj samouczek

Gratulujemy wykonanie kroków tego samouczka na Python w programie Visual Studio. W tym samouczku znasz jak:

- Tworzenie projektów i wyświetlanie zawartości projektu.
- Edytor kodu i uruchamianie projektu.
- Okno interaktywne umożliwia tworzenie nowego kodu i łatwo skopiować ten kod do edytora.
- Uruchom program ukończone w debugerze programu Visual Studio.
- Zainstaluj pakiety i zarządzanie nimi środowiska Python
- Praca z kodem w repozytorium Git

W tym miejscu zapoznaj się z pojęcia i porad prowadnice, takie jak następujące:

- [Tworzenie rozszerzenia C++ dla języka Python](working-with-c-cpp-python-in-visual-studio.md)
- [Publikowanie w usłudze Azure App Service](publishing-to-azure.md)
- [Profilowanie](profiling.md)
- [Testowanie jednostek](unit-testing.md)