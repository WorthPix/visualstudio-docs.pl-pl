---
title: Informacje o parametrach, elementy listy i szybkie informacje
ms.date: 05/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vc.tools.intellisense
helpviewer_keywords:
- Quick info
- Parameter info
- Complete word
- List members
- IntelliSense [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5e00b43f1705079a86d511239d7b38119868d8f4
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748478"
---
# <a name="intellisense-in-visual-studio"></a>IntelliSense w Visual Studio

IntelliSense jest pomoc uzupełniania kodu, który zawiera wiele funkcji: lista elementów członkowskich, informacje o parametrach, szybkie informacje i całe słowo. Funkcje te umożliwiają Aby dowiedzieć się więcej o kod, którego używasz, informacje o parametrach pisania i dodać wywołania do właściwości i metody o tylko kilku klawiszy.

Wiele aspektów IntelliSense jest specyficzne dla języków. Aby uzyskać więcej informacji o funkcji IntelliSense dla różnych języków, zobacz tematy wymienione w [Zobacz też](#see-also) sekcji.

## <a name="list-members"></a>Lista składników

Zostanie wyświetlona lista elementów prawidłową z typu (lub przestrzeni nazw), po wpisaniu znaku wyzwalacza (na przykład okres (`.`) w kodzie zarządzanym lub `::` w języku C++). Jeśli będziesz kontynuować, wpisując znaków, lista jest filtrowana do uwzględnienia tylko do elementów członkowskich, które zaczynają się od tych znaków lub których na początku *żadnych* programu word w nazwa rozpoczyna się od tych znaków. IntelliSense wykonuje także "camelcase" dopasowania, więc można po prostu wpisz pierwszą literę każdego wyrazu formatu — z uwzględnieniem wielkości liter w nazwie elementu członkowskiego, aby zobaczyć dopasowań.

Po wybraniu elementu, będzie mogło do kodu, naciskając klawisz **kartę** lub wpisując spacją. Jeśli wybierzesz element i wpiszesz kropkę, element pojawia się, a po nim kropka, co wywołuje kolejną listę elementów członkowskich. Po wybraniu elementu, ale przed jego wstawieniem, otrzymasz szybkie informacje na jego temat.

Na liście składowych ikona po lewej stronie reprezentuje typ składowej, taki jak przestrzeń nazw, klasa, funkcja lub zmienna. Listę ikony, zobacz [ikony w widoku klas i przeglądarka obiektów](../ide/class-view-and-object-browser-icons.md). Listy może być dość długo, więc możesz nacisnąć przycisk **PgUp** i **PgDn** do Przenieś w górę lub w dół na liście.

![Lista elementów członkowskich programu Visual Studio](../ide/media/vs2015_intellisense.png)

Można wywołać **członków listy** funkcji, ręcznie wpisując **Ctrl**+**J**, wybierając pozycję **Edytuj**  >  **IntelliSense** > **członków listy**, lub wybierając **członków listy** przycisk na pasku narzędzi edytora. Gdy jest wywoływana w pustym wierszu lub poza rozpoznawalnym zasięgiem, na liście wyświetlane są symbole w globalnej przestrzeni nazw.

Aby wyłączyć członków listy domyślnie (tak aby nie jest wyświetlana, jeśli wywołania), przejdź do **narzędzia** > **opcje** > **wszystkie języki**i usuń zaznaczenie **automatyczna lista członków**. Jeśli chcesz wyłączyć członków listy tylko dla określonego języka, przejdź do **ogólne** ustawień dla tego języka.

Można również przejść do trybu sugestii, w którym tylko wpisany tekst jest umieszczony w kodzie. Na przykład możesz wprowadzić identyfikator, który nie jest na liście i naciśnij klawisz **kartę**, zakończenia działania trybu zapis spowodowałoby zastąpienie identyfikatora typu. Aby przełączyć tryb uzupełniania i tryb sugestii, naciśnij klawisz **Ctrl**+**Alt**+**miejsca**, lub wybierz **Edytuj**  >  **IntelliSense** > **Przełącz tryb uzupełniania**.

## <a name="parameter-info"></a>Informacje o parametrach

Informacje o parametrach zawierają informacje na temat liczby, nazw i typów parametrów wymaganych przez metodę, parametr typu ogólnego atrybutu (w języku C#) lub szablon (w języku C++).

Parametr pogrubiony wskazuje następny parametr, który jest wymagany podczas wprowadzania funkcji. Dla funkcji przeciążenia, możesz użyć **się** i **dół** klawisze strzałek, aby wyświetlić informacje o alternatywnych parametr dla przeciążenia funkcji.

![Informacje o parametrach](../ide/media/vs2015_param_info.png)

Gdy opisujesz funkcje i parametry za pomocą komentarzy dokumentacji XML, komentarze będą wyświetlane jako informacje o parametrach. Aby uzyskać więcej informacji, zobacz [komentarze w kodzie XML podaj](../ide/supplying-xml-code-comments.md).

Informacje o parametrach można wywołać ręcznie, wybierając **Edytuj** > **IntelliSense** > **informacje o parametrach**, naciskając **Ctrl**  + **Shift**+**miejsca**, lub wybierając **informacje o parametrach** przycisk na pasku narzędzi edytora.

## <a name="quick-info"></a>Szybkie informacje

Szybkie informacje wyświetlają pełną deklarację dla każdego identyfikatora w kodzie.

![Szybkie informacje programu Visual Studio](../ide/media/vs2015_quick_info.png)

Po wybraniu elementu członkowskiego **członków listy** polu Szybkie informacje jest także wyświetlany.

![Informacje o parametrach w C&#35; pliku kodu](../ide/media/vs2015_paraminfo.png)

Szybkie informacje można wywołać ręcznie, wybierając **Edytuj** > **IntelliSense** > **szybka podpowiedź**, naciskając **Ctrl** + **I**, lub wybierając **szybka podpowiedź** przycisk na pasku narzędzi edytora.

Jeżeli funkcja jest przeciążona, mechanizm IntelliSense może nie wyświetlać informacji dla wszystkich postaci przeciążenia.

Można wyłączyć szybka podpowiedź dla kodu C++ przechodząc do **narzędzia** > **opcje** > **Edytor tekstu** > **C / C++** > **zaawansowane**, a ustawienie **automatyczna szybka podpowiedź** do `false`.

## <a name="complete-word"></a>Dokończ wyraz

Całe słowo kończy reszty zmiennej, polecenia lub nazwę funkcji po wprowadzeniu wystarczającej liczby znaków, aby usunąć niejednoznaczność terminu. Można wywołać całe słowo, wybierając **Edytuj** > **IntelliSense** > **całe słowo**, naciskając **Ctrl** + **Miejsca**, lub wybierając **całe słowo** przycisk na pasku narzędzi edytora.

## <a name="intellisense-options"></a>Opcje IntelliSense

Opcje IntelliSense są domyślnie włączone. Aby je wyłączyć, należy wybrać **narzędzia** > **opcje** > **Edytor tekstu** i usuń zaznaczenie **informacje o parametrach**lub **automatyczna lista członków** Jeśli nie chcesz, aby funkcja listy członków.

## <a name="troubleshoot-intellisense"></a>Rozwiązywanie problemów IntelliSense

W niektórych przypadkach opcje IntelliSense mogą nie działać zgodnie z oczekiwaniami.

**Gdy kursor znajduje się poniżej błąd kodu.** Nie można używać funkcji IntelliSense, jeśli funkcja niekompletne lub inny błąd nie istnieje w kodzie powyżej kursora, ponieważ nie można zanalizować elementy kodu IntelliSense. Można naprawić ten problem, zakomentowując odpowiedni kod.

**Kursor znajduje się w komentarz do kodu.** Nie można użyć funkcji IntelliSense, jeśli kursor znajduje się w komentarzu w pliku źródłowym.

**Kursor jest literałem ciągu.** Nie można użyć funkcji IntelliSense, gdy kursor znajduje się w cudzysłowie literału ciągu, jak w poniższym przykładzie:

```cpp
MessageBox( hWnd, "String literal|")
```

**Opcje automatycznego są wyłączone.** Domyślnie IntelliSense działa automatycznie, ale można ją wyłączyć. Nawet jeśli automatyczne uzupełnianie instrukcji jest wyłączone, można wywołać funkcję mechanizmu IntelliSense.

## <a name="see-also"></a>Zobacz także

- [Visual Basic IntelliSense](../ide/visual-basic-specific-intellisense.md)
- [C# IntelliSense](../ide/visual-csharp-intellisense.md)
- [Funkcja IntelliSense dla języka JavaScript](../ide/javascript-intellisense.md)
- [Zapis i refaktoryzacji kodu (C++)](/cpp/ide/writing-and-refactoring-code-cpp)
- [Podaj komentarze w kodzie XML](../ide/supplying-xml-code-comments.md)