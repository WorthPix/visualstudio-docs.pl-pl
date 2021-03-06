---
title: 'Krok 1: Tworzenie projektu aplikacji Windows Forms'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 16ac2422-e720-4e3a-b511-bc2a54201a86
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d9bcb82622a7ea303a632865b0c3f964de4b4dc3
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747658"
---
# <a name="step-1-create-a-windows-forms-application-project"></a>Krok 1: Tworzenie projektu aplikacji Windows Forms
Podczas tworzenie podglądu obrazów, pierwszym krokiem jest utworzenie projektu aplikacji Windows Forms.

 ![łącze do wideo](../data-tools/media/playvideo.gif)wersję wideo tego tematu, zobacz [samouczek 1: Tworzenie podglądu obrazów w języku Visual Basic - 1 wideo](http://go.microsoft.com/fwlink/?LinkId=205209) lub [samouczek 1: Tworzenie podglądu obrazów w języku C# - 1 wideo](http://go.microsoft.com/fwlink/?LinkId=205199). Tych klipów wideo korzysta z wcześniejszej wersji programu Visual Studio, dlatego są niewielkie różnice w niektórych poleceń menu i inne elementy interfejsu użytkownika. Jednak koncepcje i procedury działają podobnie w bieżącej wersji programu Visual Studio.

## <a name="to-create-a-windows-forms-application-project"></a>Aby utworzyć projekt aplikacji Windows Forms

1.  Na pasku menu wybierz **pliku** > **nowy** > **projektu**. Okno dialogowe powinna wyglądać następująco.

     ![Okno dialogowe nowego projektu](../ide/media/newprojectdialogcallouts.png)
**nowy projekt** — okno dialogowe

2.  Wybierz **Visual C#** lub **Visual Basic** w **zainstalowane szablony** listy.

3.  Na liście szablonów wybierz **aplikacji Windows Forms** ikony. Nazwa nowego formularza **PictureViewer**, a następnie wybierz pozycję **OK** przycisku.

     Program Visual Studio tworzy rozwiązanie programu. Rozwiązanie działa jako kontener dla wszystkich projektów i pliki wymagane przez program. Te warunki zostaną co omówiono bardziej szczegółowo w dalszej części tego samouczka.

4.  Na poniższej ilustracji przedstawiono co powinien zostać wyświetlony w interfejsie programu Visual Studio.

    > [!NOTE]
    >  Układ okna może wyglądać tak samo jak na ilustracji. Układ okna dokładne zależy od wersji programu Visual Studio, język programowania, które są używane i innych czynników. Należy jednak sprawdzić, czy są wyświetlane wszystkie trzy systemu windows.

     ![Okno środowiska IDE](../ide/media/express_ideoverview_visio.png)
**IDE** okna

     Interfejs zawiera trzy systemu windows: Okno główne, **Eksploratora rozwiązań**i **właściwości** okna.

     Jeśli brakuje żadnego z tych okien, Przywracanie domyślnego układu okien, menu, wybierając **okna** > **zresetować układ okna**. Można również wyświetlić systemu windows za pomocą poleceń menu. Na pasku menu wybierz **widoku** > **okna właściwości** lub **Eksploratora rozwiązań**. Jeśli inne okna są otwarte, zamknij je, wybierając **zamknąć** (przycisk w ich prawym górnym rogu x).

5.  Na ilustracji przedstawiono następujące okna (przejście do ruchu wskazówek zegara od lewego górnego rogu):

    -   **Okno główne** w tym oknie, należy wykonać większość pracy, takich jak pracy z formularzami i Edycja kodu. Na ilustracji, w oknie wyświetlane formularza w **Edytor formularzy**. W górnej części okna **— strona początkowa** kartę i **pliku Form1.cs [projekt]** karta jest wyświetlana. (W języku Visual Basic, nazwy karty kończy *.vb* zamiast *.cs*.)

    -   **Okno Eksploratora rozwiązań** w tym oknie można wyświetlać i przechodzić do wszystkich elementów w rozwiązaniu. Po wybraniu pliku zawartość **właściwości** okna zmiany. Po otwarciu pliku kodu (który kończy się *.cs* języka Visual C# i *.vb* w języku Visual Basic), zostanie wyświetlona projektanta dla pliku kodu lub pliku kodu. Projektant jest visual powierzchni, na którym można dodać formanty, takie jak przyciski i listy. Dla formularzy Visual Studio jest nazywany projektanta **Projektant formularzy systemu Windows**.

    -   **Okno właściwości** w tym oknie można zmienić właściwości elementów wybranych w innych oknach. Na przykład, jeśli wybierzesz Form1, można zmienić jego tytuł przez ustawienie **tekst** właściwości oraz można zmienić kolor tła ustawiając **Backcolor** właściwości.

    > [!NOTE]
    >  W pierwszym wierszu **Eksploratora rozwiązań** pokazuje **rozwiązania "PictureViewer" (1 projekt)**, co oznacza, że utworzony rozwiązania Visual Studio. To rozwiązanie może zawierać więcej niż jednego projektu, ale na razie będzie współpracować rozwiązania, które zawierają tylko jeden projekt.

6.  Na pasku menu wybierz **pliku** > **Zapisz wszystko**.

     Alternatywnie, wybierz **Zapisz wszystko** przycisk na pasku narzędzi na poniższej ilustracji przedstawiono.

     ![Zapisz wszystkie przycisku paska narzędzi](../ide/media/express_iconsaveall.png)
**Zapisz wszystko** przycisku paska narzędzi

     Visual Studio automatycznie wypełni nazwę folderu i nazwę projektu, a następnie zapisuje projekt w folderze projektów.

## <a name="to-continue-or-review"></a>Aby kontynuować lub przeglądnąć

-   Aby przejść do następnego kroku samouczka, zobacz [krok 2: uruchomienie programu](../ide/step-2-run-your-program.md).

-   Aby powrócić do temat, zobacz [samouczek 1: Tworzenie podglądu obrazów](../ide/tutorial-1-create-a-picture-viewer.md).
