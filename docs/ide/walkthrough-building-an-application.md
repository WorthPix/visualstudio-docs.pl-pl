---
title: 'Przewodnik: kompilowanie aplikacji'
ms.date: 09/25/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: af9d6476e82f37d02e1a32b1d6cb23812f0fdde5
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748221"
---
# <a name="walkthrough-build-an-application"></a>Przewodnik: kompilowanie aplikacji

Wykonując tego przewodnika, użytkownik będzie zapoznanie się ze kilka opcji, które można skonfigurować podczas tworzenia aplikacji za pomocą programu Visual Studio. Zostanie utworzenie konfiguracji niestandardowej kompilacji, Ukryj niektóre komunikaty ostrzegawcze oraz zwiększyć dane wyjściowe kompilacji dla przykładowej aplikacji.

## <a name="install-the-sample-application"></a>Instalowanie przykładowej aplikacji

Pobierz [wprowadzenie do tworzenia aplikacji WPF](https://code.msdn.microsoft.com/Introduction-to-Building-b8d16419) próbki. Wybierz opcję C# lub Visual Basic. Po *.zip* pobraniu pliku, wyodrębnij go i Otwórz *ExpenseItIntro.sln* plik za pomocą programu Visual Studio.

## <a name="create-a-custom-build-configuration"></a>Tworzenie konfiguracji niestandardowej kompilacji

Po utworzeniu rozwiązania konfiguracje debug i release kompilacji i ich domyślne elementy docelowe platformy są definiowane dla rozwiązania automatycznie. Następnie można dostosować te konfiguracje lub Utwórz swój własny. Konfiguracje kompilacji, określ typ kompilacji. Platformy kompilacji Określ system operacyjny, przeznaczonego dla aplikacji dla danej konfiguracji. Aby uzyskać więcej informacji, zobacz [omówienie konfiguracje kompilacji](../ide/understanding-build-configurations.md), [platformy kompilacji omówienie](../ide/understanding-build-platforms.md), i [porady: Ustaw debugowania i konfiguracje wydania](../debugger/how-to-set-debug-and-release-configurations.md).

Można zmienić lub utworzyć konfiguracje i ustawienia platformy przy użyciu **programu Configuration Manager** okno dialogowe. W tej procedurze utworzysz konfigurację kompilacji do testowania.

### <a name="create-a-build-configuration"></a>Tworzenie konfiguracji kompilacji

1. Otwórz **programu Configuration Manager** okno dialogowe.

   ![Tworzenie menu i poleceń programu Configuration Manager](../ide/media/buildwalk_configurationmanagerdialogbox.png)

1. W **aktywnej konfiguracji rozwiązania** wybierz  **\<nowy... \>**.

1. W **nową konfigurację rozwiązania** okno dialogowe, nazwa nowej konfiguracji `Test`, skopiować ustawienia z istniejącego **debugowania** konfiguracji, a następnie wybierz pozycję **OK**przycisku.

   ![Nowe okno dialogowe konfiguracji rozwiązania](../ide/media/buildwalk_newsolutionconfigdlgbox.png)

1. W **platformy aktywne rozwiązanie** wybierz  **\<nowy... \>**.

1. W **nowa platforma rozwiązania** oknie dialogowym wybierz **x64**, a nie kopiuje ustawień z x86 platformy.

   ![Okno dialogowe Nowy platformy rozwiązania](../ide/media/buildwalk_newsolutionplatform.png)

1. Wybierz **OK** przycisku.

   Konfiguracja aktywnego rozwiązania został zmieniony na **testu** z platformą aktywne rozwiązanie ustawioną x64.

   ![Program Configuration Manager z konfiguracji testu](../ide/media/buildwalk_configmanagertestconfig.png)

1. Wybierz **Zamknij**.

Można szybko sprawdzić lub zmienić aktywnej konfiguracji rozwiązania przy użyciu **konfiguracje rozwiązania** listy na **standardowe** paska narzędzi.

![Opcja konfiguracji rozwiązania standardowym pasku narzędzi](../ide/media/buildwalk_standardtoolbarsolutioncongfig.png)

## <a name="build-the-application"></a>Kompilowanie aplikacji

Następnie zostanie utworzenie rozwiązania z konfiguracji niestandardowej kompilacji.

### <a name="build-the-solution"></a>Skompiluj rozwiązanie

-   Na pasku menu wybierz **kompilacji** > **Kompiluj rozwiązanie**.

    **Dane wyjściowe** okno wyświetla wyniki kompilacji. Kompilacja zakończyła się pomyślnie.

## <a name="hide-compiler-warnings"></a>Ukryj ostrzeżenia kompilatora

Następnie będzie wprowadzeniu kodu powodujący ostrzeżenie ma zostać wygenerowane przez kompilator.

1. W języku C# projektu, otwórz *ExpenseReportPage.xaml.cs* pliku. W **ExpenseReportPage** metody, Dodaj następujący kod: `int i;`.

    LUB

    W projektach Visual Basic, otwórz *ExpenseReportPage.xaml.vb* pliku. W Konstruktorze niestandardowych **publicznego Sub New...** , Dodaj następujący kod: `Dim i`.

1. Skompiluj rozwiązanie.

**Dane wyjściowe** okno wyświetla wyniki kompilacji. Kompilacja zakończyła się pomyślnie, ale zostały wygenerowane ostrzeżenia:

![Dane wyjściowe okna języka Visual Basic](../ide/media/buildwalk_vbbuildoutputwnd.png)

![Program Visual C okno danych wyjściowych&#35;](../ide/media/buildwalk_csharpbuildoutputwnd.png)

Można tymczasowo ukryć niektóre komunikaty ostrzegawcze podczas kompilacji zamiast je zajmowały miejsca danych wyjściowych kompilacji.

### <a name="hide-a-specific-c-warning"></a>Ukryj określone ostrzeżenia C#

1. W **Eksploratora rozwiązań**, wybierz węzeł projektu najwyższego poziomu.

1. Na pasku menu wybierz **widoku** > **strony właściwości**.

     **Projektanta projektu** otwiera.

1. Wybierz **kompilacji** strony, a następnie w **tłumienie ostrzeżeń** Określ numer ostrzeżenia **0168**.

     ![Tworzenie strony, Projektant projektu](../ide/media/buildwalk_csharpsupresswarnings.png)

     Aby uzyskać więcej informacji, zobacz [strona kompilacji, Projektant projektu (C#)](../ide/reference/build-page-project-designer-csharp.md).

1. Skompiluj rozwiązanie.

     **Dane wyjściowe** okno wyświetla tylko informacje podsumowania dla kompilacji.

     ![Okno danych wyjściowych, Visual C&#35; kompilacji ostrzeżenia](../ide/media/buildwalk_visualcsharpbuildwarnings.png)

### <a name="suppress-all-visual-basic-build-warnings"></a>Pomiń wszystkie ostrzeżenia kompilacji Visual Basic

1. W **Eksploratora rozwiązań**, wybierz węzeł projektu najwyższego poziomu.

1. Na pasku menu wybierz **widoku** > **strony właściwości**.

     **Projektanta projektu** otwiera.

1. Na **skompilować** wybierz pozycję **Wyłącz wszystkie ostrzeżenia** pole wyboru.

     ![Strona kompilowania, Projektant projektu](../ide/media/buildwalk_vbsupresswarnings.png)

     Aby uzyskać więcej informacji, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](../ide/configuring-warnings-in-visual-basic.md).

1. Skompiluj rozwiązanie.

 **Dane wyjściowe** okno wyświetla tylko informacje podsumowania dla kompilacji.

 ![Okno danych wyjściowych, Visual Basic kompilacji ostrzeżenia](../ide/media/buildwalk_visualbasicbuildwarnings.png)

 Aby uzyskać więcej informacji, zobacz [porady: pomijanie ostrzeżeń kompilatora](../ide/how-to-suppress-compiler-warnings.md).

## <a name="display-additional-build-details-in-the-output-window"></a>Wyświetl dodatkowe kompilacji szczegóły w oknie danych wyjściowych

Można zmienić, ile informacji na temat procesu kompilacji jest wyświetlana w **dane wyjściowe** okna. Szczegółowości kompilacji jest zazwyczaj równa **minimalnego**, co oznacza, że **dane wyjściowe** okno jest wyświetlane tylko podsumowanie procesu tworzenia wraz z wysokim priorytetem ostrzeżeń i błędów. Więcej informacji na temat kompilacji można wyświetlić przy użyciu [okno dialogowe Opcje, projekty i rozwiązania, kompilacji i uruchom](../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md).

> [!IMPORTANT]
> Jeśli możesz wyświetlić więcej informacji, kompilacja zostanie potrwać dłużej.


### <a name="change-the-amount-of-information-in-the-output-window"></a>Zmień ilość informacji w oknie danych wyjściowych

1. Otwórz **opcje** okno dialogowe.

     ![Polecenie Opcje w menu Narzędzia](../ide/media/exploreide-toolsoptionsmenu.png)

1. Wybierz **projekty i rozwiązania** kategorii, a następnie wybierz pozycję **skompilować i uruchomić** strony.

1. W **poziom szczegółowości danych wyjściowych kompilacji projektu programu MSBuild** wybierz **normalny**, a następnie wybierz pozycję **OK** przycisku.

1. Na pasku menu wybierz **kompilacji** > **czystą rozwiązania**.

1. Skompiluj rozwiązanie, a następnie przejrzyj informacje w **dane wyjściowe** okna.

     Informacje o kompilacji obejmuje przy uruchomieniu kompilacji (znajdujący się na początku) i kolejność, w jakiej były przetwarzane pliki. Informacje te obejmują również składnię rzeczywiste kompilatora Visual Studio jest uruchamiany podczas kompilacji.

     Na przykład w języku C# kompilacji [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) opcja list kod ostrzeżenia **1762**, który określony wcześniej w tym temacie, wraz z trzech inne ostrzeżenia.

     W kompilacji Visual Basic [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) nie zawiera określone ostrzeżenia do wykluczenia, aby były wyświetlane nie ostrzeżenia.

    > [!TIP]
    > Umożliwia wyszukiwanie zawartości **dane wyjściowe** okno podczas wyświetlania **znaleźć** okno dialogowe, wybierając **Ctrl**+**F** klucze.

Aby uzyskać więcej informacji, zobacz [porady: wyświetlanie, zapisywanie i konfigurowanie plików dziennika kompilacji](../ide/how-to-view-save-and-configure-build-log-files.md).

## <a name="create-a-release-build"></a>Tworzenie kompilacji wydania

Można utworzyć wersję przykładowej aplikacji, która jest zoptymalizowana pod kątem wysyłania go. Dla kompilacji wydania będzie określić, że plik wykonywalny został skopiowany do udziału sieciowego, zanim kompilacji zostało rozpoczęte.

Aby uzyskać więcej informacji, zobacz [porady: zmiana budowy katalogu wyjściowego](../ide/how-to-change-the-build-output-directory.md) i [kompilacji i wyczyść projektów i rozwiązań w programie Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md).

### <a name="specify-a-release-build-for-visual-basic"></a>Określ kompilacji wydania programu Visual Basic

1. Otwórz **Projektant projektu**.

     ![Menu Widok wybierz polecenie strony właściwości](../ide/media/buildwalk_viewpropertypages.png)

1. Wybierz **skompilować** strony.

1. W **konfiguracji** wybierz **wersji**.

1. W **platformy** wybierz **x86**.

1. W **ścieżki wyjściowej kompilacji** Określ ścieżkę sieciową.

     Na przykład można określić `\\myserver\builds`.

    > [!IMPORTANT]
    > Okno komunikatu może wystąpić ostrzeżenie, że udział sieciowy, który został określony, może nie być zaufanej lokalizacji. Jeśli ufasz lokalizacji, która została określona, wybierz **OK** przycisk w oknie komunikatu.

1. Tworzenie aplikacji.

     ![Kompiluj rozwiązanie, polecenie menu kompilacji](../ide/media/exploreide-buildsolution.png)

### <a name="specify-a-release-build-for-c"></a>Określ kompilację wersji dla C# #

1. Otwórz **Projektant projektu**.

     ![Menu Widok wybierz polecenie strony właściwości](../ide/media/buildwalk_viewpropertypages.png)

1. Wybierz **kompilacji** strony.

1. W **konfiguracji** wybierz **wersji**.

1. W **platformy** wybierz **x86**.

1. W **ścieżka wyjściowa** Określ ścieżkę sieciową.

     Na przykład można określić `\\myserver\builds`.

    > [!IMPORTANT]
    > Okno komunikatu może wystąpić ostrzeżenie, że udział sieciowy, który został określony, może nie być zaufanej lokalizacji. Jeśli ufasz lokalizacji, która została określona, wybierz **OK** przycisk w oknie komunikatu.

1. Na **standardowym pasku narzędzi**, Ustaw konfiguracje rozwiązania **wersji** i platformy rozwiązania **x86**.

1. Tworzenie aplikacji.

     ![Kompiluj rozwiązanie, polecenie menu kompilacji](../ide/media/exploreide-buildsolution.png)

   Plik wykonywalny jest kopiowany do określonej ścieżki sieciowej. Jego ścieżka byłaby `\\myserver\builds\\FileName.exe`.

Gratulacje: zakończyła się pomyślnie w tym przewodniku.

## <a name="see-also"></a>Zobacz także

- [Wskazówki: Tworzenie projektu (C++)](/cpp/ide/walkthrough-building-a-project-cpp)
- [Omówienie wstępnej kompilacji projektu aplikacji sieci web ASP.NET](http://msdn.microsoft.com/b940abbd-178d-4570-b441-52914fa7b887)
- [Wskazówki: Użyj programu MSBuild](../msbuild/walkthrough-using-msbuild.md)