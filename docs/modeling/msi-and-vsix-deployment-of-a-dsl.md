---
title: Wdrażanie pakietów MSI i VSIX języka DSL
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: c8a7c88c0c1808b5155ada9d46cfbdad9edd5cf5
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2018
ms.locfileid: "47859357"
---
# <a name="msi-and-vsix-deployment-of-a-dsl"></a>Wdrażanie pakietów MSI i VSIX języka DSL
Języka specyficznego dla domeny można zainstalować na komputerze lokalnym lub na innych komputerach. Program Visual Studio muszą być zainstalowane na komputerze docelowym.

## <a name="which"></a> Wybieranie między wdrażanie pliku MSI i VSIX
 Istnieją dwie metody wdrażania języka specyficznego dla domeny:

|Metoda|Zalety|
|------------|--------------|
|VSX (z rozszerzeniem programu Visual Studio)|Bardzo łatwa do wdrożenia: kopiowania, a następnie wykonaj **.vsix** pliku z projektem DslPackage.<br /><br /> Aby uzyskać więcej informacji, zobacz [instalowania i odinstalowywania DSL za pomocą VSX](#Installing).|
|MSI (plik Instalatora)|— Umożliwia użytkownikowi Otwórz program Visual Studio, klikając dwukrotnie plik DSL.<br />-Kojarzy ikony z typem pliku DSL na komputerze docelowym.<br />-Kojarzy XSD (schematu XML) z typem pliku DSL. Umożliwia to uniknięcie ostrzeżenia, gdy plik jest ładowany do programu Visual Studio.<br /><br /> Projektu Instalatora należy dodać do rozwiązania, aby utworzyć instalatora MSI.<br /><br /> Aby uzyskać więcej informacji, zobacz [wdrażania DSL za pomocą pliku MSI](#msi).|

## <a name="Installing"></a> Instalowanie i odinstalowywanie DSL za pomocą VSX
 Gdy DSL jest instalowany przez tę metodę, użytkownik może otwierać plik DSL z programu Visual Studio, ale nie można otworzyć pliku w Eksploratorze Windows.

#### <a name="to-install-a-dsl-by-using-the-vsx"></a>Aby zainstalować DSL za pomocą VSX

1.  Na komputerze, należy znaleźć **.vsix** pliku, który został zbudowany przez projekt pakietu języka DSL.

    1.  W **Eksploratora rozwiązań**, kliknij prawym przyciskiem myszy **DslPackage** projektu, a następnie kliknij przycisk **Otwórz Folder w Eksploratorze Windows**.

    2.  Zlokalizuj plik **bin\\\*\\**_YourProject_**. DslPackage.vsix**

2.  Kopiuj **.vsix** plik na komputer docelowy, na którym chcesz zainstalować język DSL. Może to być Twój własny komputer lub innej.

    -   Komputer docelowy musi mieć jedną z wersji [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] obsługujący języków DSL w czasie wykonywania. Aby uzyskać więcej informacji, zobacz [obsługiwane wersje programu Visual Studio dla zestawu Visualization & Modeling SDK](../modeling/supported-visual-studio-editions-for-visualization-amp-modeling-sdk.md).

    -   Komputer docelowy musi mieć jedną z wersji programu Visual Studio, określone w **DslPackage\source.extensions.manifest**.

3.  Na komputerze docelowym, kliknij dwukrotnie **.vsix** pliku.

     **Instalator rozszerzenia programu Visual Studio** otwiera i instaluje rozszerzenia.

4.  Uruchom lub uruchom ponownie [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].

5.  Aby przetestować język DSL, przy użyciu programu Visual Studio Utwórz nowy plik, który ma rozszerzenie które są zdefiniowane dla DSL.

#### <a name="to-uninstall-a-dsl-that-was-installed-by-using-vsx"></a>Aby odinstalować DSL, który został zainstalowany przy użyciu VSX

1.  Na **narzędzia** menu, kliknij przycisk **Menedżera rozszerzeń**.

2.  Rozwiń **zainstalowanych rozszerzeń**.

3.  Wybierz rozszerzenie, w którym zdefiniowano język DSL, a następnie kliknij **Odinstaluj**.

 Rzadko wadliwe rozszerzenie nie ładuje się i tworzy raport w oknie błędów, ale nie są wyświetlane w Menedżerze rozszerzeń. W takim przypadku należy usunąć rozszerzenie przez usunięcie pliku:

 *LocalAppData* **\Microsoft\VisualStudio\10.0\Extensions**

## <a name="msi"></a> Wdrażanie DSL w Instalatora MSI
 Definiując plik MSI (Instalator Windows) dla DSL, możesz zezwolić użytkownicy będą mogli otwierać pliki DSL z programu Windows Explorer. Można również skojarzyć ikonę i krótki opis z rozszerzeniem nazwy pliku. Ponadto plik MSI można zainstalować pliku XSD, który może służyć do sprawdzania poprawności plików DSL. Jeśli chcesz, możesz dodać inne składniki, do pliku MSI, który zostanie zainstalowany w tym samym czasie.

 Aby uzyskać więcej informacji na temat plików MSI i inne opcje wdrażania, zobacz [wdrażania aplikacji, usług i składników](../deployment/deploying-applications-services-and-components.md).

 Aby utworzyć instalatora MSI, dodajesz projektu Instalatora do rozwiązania programu Visual Studio. Najprostsza metoda tworzenia projektu konfiguracji jest użycie szablonu CreateMsiSetupProject.tt, który można pobrać z [witryny VMSDK](http://go.microsoft.com/fwlink/?LinkID=186128).

#### <a name="to-deploy-a-dsl-in-an-msi"></a>Aby wdrożyć DSL w Instalatora MSI

1.  Ustaw `InstalledByMsi` w manifeście rozszerzenia. Zapobiega to VSX jest instalowana i odinstalowywana z wyjątkiem za pomocą pakietu MSI. Jest to ważne, jeśli będzie obejmować inne składniki w pliku MSI.

    1.  Open DslPackage\source.extension.tt

    2.  Wstaw następujący wiersz przed `<SupportedProducts>`:

        ```xml
        <InstalledByMsi>true</InstalledByMsi>
        ```

2.  Utwórz lub Edytuj ikonę która będzie reprezentować DSL w Eksploratorze Windows. Na przykład edytować **DslPackage\Resources\File.ico**

3.  Upewnij się, że następujące atrybuty DSL są prawidłowe:

    -   W Eksplorator DSL kliknij węzeł główny i przejrzyj w oknie właściwości:

        -   Opis

        -   Wersja

    -   Kliknij przycisk **edytora** węzła i w oknie dialogowym właściwości kliknij **ikonę**. Ustaw wartość na odwoływać się do pliku ikony w **DslPackage\Resources**, takich jak **File.ico**

    -   Na **kompilacji** menu Otwórz **programu Configuration Manager**i wybierz konfigurację, który chcesz utworzyć, takie jak **wersji** lub **debugowania** .

4.  Przejdź do [wizualizacji i modelowania SDK strony głównej](http://go.microsoft.com/fwlink/?LinkID=186128)i z **pliki do pobrania** pozycję Pobierz **CreateMsiSetupProject.tt**.

5.  Dodaj **CreateMsiSetupProject.tt** do projektu Dsl.

     Visual Studio utworzy plik o nazwie **CreateMsiSetupProject.vdproj**.

6.  W Eksploratorze Windows skopiuj Dsl\\*.vdproj w nowym folderze o nazwie Instalatora.

     (Jeśli chcesz, możesz teraz wykluczyć CreateMsiSetupProject.tt z projektu języka Dsl.)

7.  W **Eksploratora rozwiązań**, Dodaj **instalacji\\\*vdproj** jako istniejący projekt.

8.  Na **projektu** menu, kliknij przycisk **zależności projektu**.

     W **zależności projektu** okna dialogowego Wybierz projekt Instalatora.

     Zaznacz pole obok pozycji **DslPackage**.

9. Ponownie skompiluj rozwiązanie.

10. W Eksploratorze Windows znajdź utworzone pliku MSI w swojej instalacji projektu.

     Skopiuj plik MSI na komputerze, na którym chcesz zainstalować DSL. Kliknij dwukrotnie plik MSI. Jest uruchamiany Instalator.

11. Na komputerze docelowym Utwórz nowy plik, który ma rozszerzenie pliku DSL. Upewnij się, że:

    -   W widoku listy Eksploratora Windows plik zostanie wyświetlony ikonę i opis, który został zdefiniowany.

    -   Gdy kliknij dwukrotnie plik, Visual Studio uruchomi się i otwiera plik DSL w edytorze języka DSL.

 Jeśli wolisz, projektu Instalatora można utworzyć ręcznie, zamiast używać szablonu tekstu. Aby uzyskać wskazówki, która zawiera tę procedurę, zobacz rozdział 5 [wizualizacji i modelowania SDK laboratorium](http://go.microsoft.com/fwlink/?LinkId=208878).

#### <a name="to-uninstall-a-dsl-that-was-installed-from-an-msi"></a>Aby odinstalować DSL, który został zainstalowany z pliku MSI

1.  Windows, otwórz **programy i funkcje** Panelu sterowania.

2.  Odinstaluj język DSL.

3.  Uruchom ponownie program Visual Studio.