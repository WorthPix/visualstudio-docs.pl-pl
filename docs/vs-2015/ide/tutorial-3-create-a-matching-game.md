---
title: 'Samouczek 3: Tworzenie pasujący obiekt typu gier | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 525815c8-2845-45e8-be96-100d1f144725
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e8742924e1693a79268d6a35bc266caf5c5f32ec
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49259101"
---
# <a name="tutorial-3-create-a-matching-game"></a>Samouczek 3: Tworzenie gry w dopasowywanie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

W tym samouczku stworzysz grę w dopasowywanie, gdzie gracz musi dopasować pary ukrytych ikon. Dowiesz się, jak:  
  
-   Store obiektów, takich jak ikony, w `List` obiektu.  
  
-   Użyj `foreach` pętli w języku Visual C# lub `For Each` pętli w języku Visual Basic do iteracji przez elementy na liście.  
  
-   Śledzić stan formularza za pomocą zmiennych odwołania.  
  
-   Stworzyć program obsługi zdarzeń w celu reagowania na zdarzenia, którego możesz używać z wieloma obiektami.  
  
-   Stworzyć czasomierz, który odlicza czas do zera, a następnie uruchamia zdarzenie dokładnie jeden raz po uruchomieniu.  
  
 Po zakończeniu samouczka program będzie wyglądać tak, jak na poniższej ilustracji.  
  
 ![Gra tworzona w ramach tego samouczka](../ide/media/express-finishedgame.png "Express_FinishedGame")  
Gra tworzona w ramach tego samouczka  
  
 Aby pobrać pełną wersję przykładu, zobacz [przykładowy samouczek gry w dopasowywanie pełną](http://code.msdn.microsoft.com/Complete-Matching-Game-4cffddba).  
  
> [!NOTE]
>  W tym samouczku omówiono zarówno Visual C#, jak i Visual Basic, więc skoncentruj się na informacjach specyficznych dla języka programowania, którego używasz.  
  
 Jeśli masz problem lub pytania dotyczące programowania, spróbuj zadać pytanie na jednym z forów MSDN. Zobacz [Forum języka Visual Basic](http://social.msdn.microsoft.com/Forums/home?forum=vbgeneral) i [Forum Visual C#](http://social.msdn.microsoft.com/Forums/home?forum=csharpgeneral). Dostępne są tam również wspaniałe, bezpłatne materiały szkoleniowe wideo. Aby dowiedzieć się więcej na temat programowania w języku Visual Basic, zobacz [Visual Basic Fundamentals: Development for Absolute Beginners](http://channel9.msdn.com/Series/Visual-Basic-Development-for-Absolute-Beginners). Aby dowiedzieć się więcej na temat programowania w języku Visual C#, zobacz [C# Fundamentals: Development for Absolute Beginners](http://channel9.msdn.com/Series/C-Sharp-Fundamentals-Development-for-Absolute-Beginners).  
  
## <a name="related-topics"></a>Tematy pokrewne  
  
|Tytuł|Opis|  
|-----------|-----------------|  
|[Krok 1. Tworzenie projektu i dodawanie tabeli do formularza](../ide/step-1-create-a-project-and-add-a-table-to-your-form.md)|Rozpocznij od stworzenia projektu i dodawanie `TableLayoutPanel` formantu, aby zachować formanty prawidłowo wyrównane.|  
|[Krok 2. Dodawanie obiektu Random i listy ikon](../ide/step-2-add-a-random-object-and-a-list-of-icons.md)|Dodaj `Random` obiektu i `List` obiekt, aby utworzyć listę ikon.|  
|[Krok 3. Przypisanie losowej ikony do każdej etykiety](../ide/step-3-assign-a-random-icon-to-each-label.md)|Przypisz ikony losowo do `Label` kontroluje, tak aby każda gra była inna.|  
|[Krok 4. Dodawanie procedury obsługi zdarzeń kliknięcia do każdej etykiety](../ide/step-4-add-a-click-event-handler-to-each-label.md)|Dodaj program obsługę zdarzeń Kliknij, który zmienia kolor klikniętej etykiety.|  
|[Krok 5. Dodawanie odwołań do etykiet](../ide/step-5-add-label-references.md)|Dodaj zmienne odwołania, aby śledzić, które etykiety zostały kliknięte.|  
|[Krok 6. Dodawanie czasomierza](../ide/step-6-add-a-timer.md)|Dodaj czasomierz do formularza, aby śledzić czas, który upłynął w grze.|  
|[Krok 7. Zachowanie widoczności par](../ide/step-7-keep-pairs-visible.md)|Zachowaj widoczne pary ikon, jeśli wybrana para pasuje.|  
|[Krok 8. Dodanie metody sprawdzania, czy gracz wygrał](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md)|Dodaj `CheckForWinner()` metodę, aby sprawdzić, czy gracz wygrał.|  
|[Krok 9. Wypróbowanie innych funkcji](../ide/step-9-try-other-features.md)|Wypróbuj inne funkcje, takie jak zmiana ikon i kolorów, dodawanie siatki i dodawanie dźwięków. Spróbuj powiększyć planszę i dostosować czasomierz.|



