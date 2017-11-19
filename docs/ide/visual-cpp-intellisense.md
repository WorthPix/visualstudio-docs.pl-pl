---
title: Visual C++ Intellisense | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d7c6414-4e6c-4889-a74c-a6033795eccc
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 88ef1657438cd2073b2f3219739c8236eb94bc2c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="visual-c-intellisense"></a>Intellisense dla programu Visual C++
W programie Visual Studio 2015 IntelliSense jest dostępne dla pojedynczego kodu plików oraz jak w przypadku plików w projektach. W projektach między platformami niektóre funkcje IntelliSense są dostępne w .cpp i .c pliki w projekcie udostępnionym kodu nawet wtedy, gdy znajdują się w kontekście systemu Android lub iOS.  
  
## <a name="intellisense-features-in-c"></a>Funkcje IntelliSense w języku C++  
 IntelliSense jest nazwa nadana zestaw funkcji, które kodowania wygodniejsze. Ponieważ różne osoby mają różne poznać co to jest wygodne, można niemal wszystkie funkcje IntelliSense włączone lub wyłączone w **Edytor tekstu, C/C++, zaawansowane** strony właściwości.  
  
 ![Narzędzia, opcje, Edytor tekstu, C &#47; & C &43; 43; zaawansowane](../ide/media/sintellisensecpptoolsoptions.PNG "sIntelliSenseCppToolsOptions")  
  
 Elementy menu i skróty klawiaturowe pokazano na poniższej ilustracji umożliwia dostęp do funkcji IntelliSense.  
  
 ![Visual C &43; &#43; IntelliSense Menu](../ide/media/vs2015_cpp_intellisense_menu.png "vs2015_cpp_intellisense_menu")  
  
### <a name="statement-completion-and-member-list"></a>Listy uzupełniania i element członkowski — instrukcja  
 Po ponownym uruchomieniu, wpisując słowa kluczowego, typu, funkcji, nazwa zmiennej lub innego elementu programu rozpoznającego przez kompilator, Edytor umożliwia dokończyć słowa  
  
 Listę ikon i ich znaczenie, zobacz [Widok klas i przeglądarka obiektów ― ikony](../ide/class-view-and-object-browser-icons.md).  
  
 ![Visual C &43; &#43; Okno programu Word zakończenia](../ide/media/vs2015_cpp_complete_word.png "vs2015_cpp_complete_word")  
  
 Lista elementów członkowskich jest wywoływana po raz pierwszy pokazywane są tylko elementy członkowskie, które są dostępne dla bieżącego kontekstu. Jeśli używasz **Ctrl + J** po, który zawiera wszystkie elementy członkowskie niezależnie od dostępności. Jeśli wywołanie raz trzeci go jeszcze większą listę elementów programu jest wyświetlany. Można wyłączyć uzupełniania w **Opcje ogólne C/C++** strony.  
  
 ![Visual C &43; &#43; Lista elementów członkowskich](../ide/media/vs2015_cpp_list_members.png "vs2015_cpp_list_members")  
  
### <a name="parameter-help"></a>Parametr pomocy  
 Po wpisaniu nawiasu otwierającego wywołanie funkcji lub nawias w deklaracji zmiennej szablonu klasy Edytor pokazuje małe okno z typami parametrów dla każdego przeciążenia funkcji lub konstruktora. Parametr "bieżący"--na podstawie lokalizacji kursora — jest pogrubione. Można wyłączyć uzupełniania w **Opcje ogólne C/C++** strony.  
  
 ![Visual C &43; &#43; Parametr pomocy](../ide/media/vs_2015_cpp_param_help.png "vs_2015_cpp_param_help")  
  
### <a name="quick-info"></a>Szybkie informacje  
 Po umieszczeniu kursora myszy na zmienną małych okno jest wyświetlane w tekście, który zawiera informacje o typie i nagłówek, w którym jest zdefiniowany typ. Aktywuj wywołanie funkcji, aby wyświetlić podpisu funkcji. Można wyłączyć szybkie informacje w **Edytor tekstu, C/C++, zaawansowane** strony.  
  
 ![Visual C &43; &#43; Skrócone informacje](../ide/media/vs2015_cpp_quickinfo.png "vs2015_cpp_quickInfo")  
  
## <a name="error-squiggles"></a>Zygzaki sygnalizujące błędy  
 Zygzaki pod elementem programu (zmiennej, słowo kluczowe, nawias klamrowy, wpisz nazwę i tak dalej) wywołać uwagę błąd lub potencjalnych błędów w kodzie. Zielony wężyk pojawia się podczas pisania deklaracja przekazująca dalej w celu odnotowania, konieczność zapisania implementacji. Purpurowa wężyk w projekcie udostępnionym jest wyświetlany błąd w kodzie, który nie jest obecnie aktywny, na przykład podczas pracy w kontekście systemu Windows, ale coś wprowadź, która byłaby błędu w kontekście systemu Android. Czerwona falista wskazuje błąd kompilatora lub ostrzeżenie w aktywnej kod, który należy rozwiązać.  
  
 ![Visual C &43; &#43; Błąd zygzaki](../ide/media/vs2015_cpp_error_quiggles.png "vs2015_cpp_error_quiggles")  
  
## <a name="code-colorization-and-fonts"></a>Kolorowanie kodu i czcionek  
 Domyślne kolorów i czcionek można zmieniać za pomocą **środowiska, czcionki i kolory** strony właściwości. Można zmienić czcionki dla wielu interfejsu użytkownika systemu windows w tym miejscu nie tylko edytora. Ustawienia, które są specyficzne dla języka C++ rozpoczynać się od "C++"; inne ustawienia są dla wszystkich języków.  
  
## <a name="cross-platform-intellisense"></a>IntelliSense i Platform  
 W projekcie udostępnionym kodu niektóre funkcje IntelliSense, takie jak zygzaki są dostępne, nawet wtedy, gdy użytkownik pracuje w kontekście systemu Android. Jeśli piszesz niektórych kod, który może spowodować błąd w projekcie jest nieaktywny, pozostanie zygzaki funkcji IntelliSense, ale znajdują się w innym kolorze niż zygzaki błędów w bieżącym kontekście.  
  
 Oto OpenGLES aplikacji, która jest skonfigurowana dla kompilacji dla systemów Android i iOS. Na ilustracji przedstawiono udostępnionego kodu edytowany. W pierwszym obrazu systemu Android jest aktywnym projektem:  
  
 ![Projekt systemu Android jest aktywnym projektem. ] (../ide/media/intellisensecppcrossplatform.png "IntelliSenseCppCrossPlatform")  
  
 Należy zauważyć, że:  
  
-   #Else gałęzi w wierszu 8 będzie szary, aby wskazać regionu nieaktywnych, ponieważ __ANDROID\_ \_ jest zdefiniowany dla systemu android.  
  
-   Zmienna pozdrowienia w wierszu 11 został zainicjowany z identyfikatorem HELLO, mającej wężyk purpurowy. Jest tak, ponieważ nie identyfikatora HELLO nie została zdefiniowana w projekcie aktualnie nieaktywne w systemie iOS. Gdy w systemie Android czy skompilować projekt wiersza 11, nie będzie w systemie iOS. Ponieważ jest to udostępniony kod, który nie jest należy zmienić nawet kompiluje w aktualnie aktywnej konfiguracji.  
  
-   W wierszu 12 znajduje się czerwona falista na podstawie identyfikatora BYE; Ten identyfikator nie jest zdefiniowany w obecnie zaznaczonej aktywnego projektu.  
  
 Teraz Zmień aktywnego projektu iOS.StaticLibrary i zwróć uwagę, jak zmienić zygzaki.  
  
 ![iOS został wybrany jako aktywnego projektu. ] (../ide/media/intellisensecppcrossplatform2.png "IntelliSenseCppCrossPlatform2")  
  
 Należy zauważyć, że:  
  
-   Gałęzi #ifdef w wierszu 6 będzie szary, aby wskazać regionu nieaktywnych, ponieważ __ANDROID\_ \_ nie jest zdefiniowany dla projektu iOS.  
  
-   Zmienna pozdrowienia w wierszu 11 został zainicjowany z identyfikatorem HELLO, który ma teraz czerwona falista. Jest tak, ponieważ nie identyfikatora HELLO nie została zdefiniowana w projekcie iOS aktualnie aktywny.  
  
-   Wiersz 12 ma purpurowa wężyk na podstawie identyfikatora BYE; Ten identyfikator nie jest zdefiniowany w aktualnie nieaktywne Android.NativeActivity projektu.  
  
## <a name="single-file-intellisense"></a>Pojedynczy plik IntelliSense  
 Po otwarciu pojedynczego pliku poza żadnego projektu nadal otrzymywać IntelliSense. Można włączyć lub wyłączyć określonymi funkcjami, przechodząc do **Edytor tekstu, C/C++, zaawansowane** można włączyć lub wyłączyć funkcje IntelliSense. Aby skonfigurować IntelliSense dla pojedynczych plików, które nie są częścią projektu, należy wyszukać **IntelliSense i przeglądanie dla plików poza projektami** w **zaawansowane** sekcji. Zobacz [Przewodnik po Visual C++](http://msdn.microsoft.com/en-us/499cb66f-7df1-45d6-8b6b-33d94fd1f17c).  
  
 ![Visual C &43; &#43; pojedynczy plik intellisense](../ide/media/vs2015_cpp_single_file_intellisense.png "vs2015_cpp_single_file_intellisense")  
  
 Domyślnie IntelliSense używane tylko standardowe obejmują pojedynczy plik katalogów można znaleźć plików nagłówka. Aby dodać dodatkowe katalogi, otwórz menu skrótów w węźle rozwiązania i Dodaj katalog na **debugowania kodu źródłowego** listy, jak przedstawiono na poniższej ilustracji:  
  
 ![Dodawanie ścieżki do pliku nagłówka. ] (../ide/media/intellisensedebugyourcode.jpg "IntelliSenseDebugYourCode")  
  
## <a name="see-also"></a>Zobacz też  
 [Korzystanie z IntelliSense](../ide/using-intellisense.md)