---
title: Interfejs użytkownika debugera (XSLT)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: 846fdabd-e5c3-4688-9b0d-a93fbeea1b96
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: df50443a4a86e1524f20fa61275364b7c6603fdf
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/20/2018
ms.locfileid: "39176027"
---
# <a name="debugger-user-interface-xslt"></a>Interfejs użytkownika debugera (XSLT)

W tym temacie opisano okien debugera i oknach dialogowych. Zostało omówione tylko elementów interfejsu użytkownika, których zachowanie debugowania specyficznych dla XSLT.

Aby uzyskać więcej informacji, zobacz [debugowanie odwołań do interfejsu użytkownika](../debugger/debugging-user-interface-reference.md).

## <a name="locals-window"></a>okno zmiennych lokalnych
 Okno zmiennych lokalnych Wyświetla informacje o wszelkie zmienne zdefiniowane w arkuszu stylów. Okno zmiennych lokalnych zawiera trzy kolumny informacji:

 **Nazwa**

 Ta kolumna zawiera nazwy wszystkich zmiennych lokalnych w bieżącym zakresie. Węzeł zestawy mają kontrolką drzewa, które użytkownik może Przechodzenie do szczegółów wyświetlić jego podfolderów.

 **Wartość**

 Ta kolumna zawiera wartości zawarte w każdej zmiennej. Atrybut, przetwarzania instrukcji, komentarz, tekst i węzły CData wyświetlane wartości tekstowej węzła. Węzły Namespace wyświetlają identyfikator URI przestrzeni nazw.

 **Typ**

 Ta kolumna określa typ danych dla każdej zmiennej, na liście **nazwa** kolumny.

 Okno zmiennych lokalnych wyświetla także zmienne kontekstowe wstępnie zdefiniowanych, które śledzą kontekście transformację XSLT. W poniższej tabeli opisano zmienne kontekstowe wstępnie zdefiniowanych, używany przez debuger XSLT.

|Nazwa|Opis|
|----------|-----------------|
|`last()`|Rozmiar kontekstu.|
|`position()`|Pozycja lub numer indeksu węzła kontekstu, względem rozmiar kontekstu.|
|`self::node()`|Wartość węzła kontekstu.|

## <a name="output-window"></a>Okno wyniku
 W oknie danych wyjściowych pokazuje wszystkie komunikaty o błędach lub wyjątki zabezpieczeń, które występują podczas debugowania.

 Debuger XSLT używa oddzielne okno do wyświetlania danych wyjściowych debugera. To jest tym samym oknie używany do wyświetlania danych wyjściowych z **wyświetlanie danych wyjściowych XSL** polecenia.

## <a name="task-list"></a>Lista zadań
 **Listy zadań** zawiera listę wszystkich błędów kompilacji w arkuszu stylów. Dwukrotnie błąd przenosi kursor do wiersza z powodu błędu.

 **Listy zadań** zawiera błędy, które występują w blokach skryptu w pliku XSLT.

> [!NOTE]
> Debuger XSLT nie zawiera ostrzeżeń, więc nigdy nie pojawiają się na **listy zadań**.

## <a name="breakpoints-window"></a>Okno punktów przerwania
 Okno punktów przerwania pokazuje wszystkie punkty przerwania ustawione w bieżącym projekcie. Jeśli punkt przerwania jest dodawany, gdy okno jest w widoku, okno jest automatycznie aktualizowany, aby wyświetlić nowy punkt przerwania.

 Okno punktów przerwania, powinny zachowywać się w taki sam sposób jak inne debugery programu Visual Studio.

## <a name="command-windowimmediate-window"></a>Okno polecenia/bezpośrednim
 Nie jest zaimplementowana w tej wersji w debugerze XSLT.

## <a name="watch-window"></a>okno czujki
 Okno czujki, jest używane do oceny zmiennych. Można również zmienić wartości zmiennych.

 Zmienne okno czujki związanych z bieżącego kontekstu (element najważniejsze dla stosu wywołań). W przypadku zmiany kontekstu okno czujki aktualizacji i wyświetla zmienne ustawione dla tego kontekstu.

## <a name="call-stack-window"></a>Stos wywołań, okno
 **Stos wywołań** okno służy do wyświetlania nazwy funkcji na stosie wywołań, typy parametrów i wartości parametrów. Informacje stosu wywołań jest wyświetlany tylko wtedy, gdy program debugowany jest w stanie przerwania.

 Stos wywołań reprezentuje różnych kontekstach, które przechodzi wykonywania XSLT. Na przykład, jeśli jest połączenie z tego szablonu, "a" do szablonu "b", szablon "" i szablon "b", pojawiają się w **stos wywołań** okno z bieżącego kontekstu na samej górze listy. Użytkownik jest w stanie się zapytanie, które jest w trakcie wykonywania.

 Jeśli szablony nie mają nazwy w pliku XSLT, generowania procesora XSLT nazw są używane.

 Kliknięcie elementu na innym niż u góry listy wskazuje w podglądzie, gdzie gałąź wykonywania XSLT się stało, przy użyciu standardowych zielone Podświetlenie i zielone strzałki.

## <a name="quickwatch-dialog-box"></a>QuickWatch — okno dialogowe
 **QuickWatch** okno dialogowe służy do oceny wyrażenia XPath 1.0. Węzeł kontekstu ( `self::node()` węzła z okna zmienne lokalne) udostępnia kontekst umożliwiający wykonanie wyrażenie XPath. Wynik wykonania wyrażenie XPath jest wyświetlany w oknie czujki.

 Poniższa lista zawiera pewne ograniczenia dotyczące oceny wyrażenia XPath.

-   Dozwolone są tylko wbudowane funkcje XPath.

-   XSLT wbudowane funkcje, takie jak `document()`, `key()`i tak dalej, nie są dozwolone.

-   Funkcje zdefiniowane przez użytkownika nie są dozwolone.

Aby uzyskać więcej informacji, zobacz [instrukcje: Ocena wyrażenia XPath](../xml-tools/how-to-evaluate-an-xpath-expression.md).

## <a name="disassembly-window"></a>Dezasemblacja, okno
 Okno dezasemblacji zawiera kod zestawu, który jest generowany przez kompilator XSLT. Tego okna może służyć w taki sam sposób, jak wszystkie inne okna dezasemblacji programu Visual Studio.

 Aby uzyskać więcej informacji [porady: Korzystanie z okna dezasemblacji](../debugger/how-to-use-the-disassembly-window.md).

## <a name="see-also"></a>Zobacz także

- [Debugowanie kodu XSLT](../xml-tools/debugging-xslt.md)
- [Podstawowe informacje o debugerze](../debugger/getting-started-with-the-debugger.md)
- [Sprawdzanie zmiennych w oknach zmiennych automatycznych i zmiennych lokalnych w programie Visual Studio](../debugger/autos-and-locals-windows.md)