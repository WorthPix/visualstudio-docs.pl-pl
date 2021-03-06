---
title: Opcje, Edytor tekstu wszystkie języki | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.JavaScript.General
- VS.ToolsOptionsPages.Text_Editor.ResJSON.General
- vs.toolsoptionspages.text_editor.all_languages.scrollbars
helpviewer_keywords:
- Text Editor Options dialog box
- statement completion
- word wrap
- General dialog box
- line numbers
- virtual space
ms.assetid: 49ee7306-9d46-4170-850f-a1716171752d
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2584f56e31dea55ff7a4d67b61b8c7453ade4c10
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49255713"
---
# <a name="options-text-editor-all-languages"></a>Opcje, edytor tekstu, wszystkie języki
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
To okno dialogowe pozwala zmienić domyślne zachowanie edytora kodu. Te ustawienia mają zastosowanie również do innych edytorów oparte na kod edytora, takiego jak widok źródła w Projektancie HTML. Aby otworzyć to okno dialogowe, wybierz **opcje** z **narzędzia** menu. W ramach **edytora tekstów** folder, rozwiń węzeł **wszystkie języki** podfolder, a następnie wybierz **ogólne**.  
  
> [!CAUTION]
>  Ta strona ustawia domyślne opcje dla wszystkich języków programowania. Należy pamiętać, że zresetowanie opcji, w tym oknie dialogowym przywróci ogólne opcje we wszystkich językach niezależnie od opcji wybranych są w tym miejscu. Aby zmienić opcje edytora tekstowego dla tylko jednego języka, rozwiń podfolder dla danego języka, a następnie wybierz jego stron opcji.  
  
 Wygaszone znacznik wyboru jest wyświetlane, gdy po wybraniu opcji na stronach opcji ogólnych dla niektórych języków programowania, ale nie dla innych użytkowników.  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [Dostosowywanie ustawień środowiska deweloperskiego, w programie Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="statement-completion"></a>Dokańczanie instrukcji  
 Automatyczna lista członków  
 Po wybraniu wyskakującego listy dostępne elementy członkowskie, właściwości, wartości lub metody są wyświetlane przez technologię IntelliSense podczas wpisywania w edytorze. Wybierz dowolny element z wyskakującej listy do podawania pozycji w kodzie. Wybranie tej opcji umożliwia **kryj składowe zaawansowane** opcji.  
  
 Kryj składowe zaawansowane  
 Po wybraniu skraca uzupełniania instrukcji wyskakujące, wyświetlając tylko te elementy, które są używane najczęściej. Inne elementy są odfiltrowywane z listy.  
  
 Informacje o parametrach  
 Po wybraniu pełną składnię bieżącej deklaracji lub procedura jest wyświetlana w obszarze punkt wstawiania w edytorze, ze wszystkimi jego dostępnych parametrów. Następny parametr, które można przypisać jest wyświetlany czcionką pogrubioną.  
  
## <a name="settings"></a>Ustawienia  
 Włączyć wirtualną przestrzeń  
 Gdy ta opcja jest zaznaczona i **zawijanie wyrazów** jest wyczyszczone, można kliknąć dowolne miejsce poza końcem wiersza w edytorze kodu i typu. Ta funkcja może służyć do pozycji Komentarze w momencie spójne obok kodu.  
  
 Zawijanie wyrazów  
 Po wybraniu dowolnej części wiersza, który mieści się w poziomie w obszarze edytora w widoczne jest automatycznie wyświetlana w następnym wierszu. Wybranie tej opcji umożliwia **Pokaż zualne przy zawijaniu wierszy** opcji.  
  
> [!NOTE]
>  **Wirtualną przestrzenią** włączenia funkcji wyłączone podczas **zawijanie** znajduje się na.  
  
 Pokaż zualne przy zawijaniu wierszy  
 Po wybraniu wskaźnik zwracany strzałkę jest wyświetlany, gdy długi wiersz zawijana drugi wiersz.  
  
 ![LineBreakSymbol — zrzut ekranu](../../ide/reference/media/linebreak.gif "linebreak")  
  
 Usuń zaznaczenie tej opcji, jeśli nie chcesz wyświetlić te wskaźniki.  
  
> [!NOTE]
>  Tych strzałek monitu nie są dodawane do kodu, a nie do drukowania. Są one tylko do celów referencyjnych.  
  
 Zastosuj poleceń Wytnij lub Kopiuj do pustych wierszy, jeśli nie zaznaczono żadnego fragmentu  
 Ta opcja ustawia zachowanie edytora, gdy umieścisz kursor w pustym wierszu, wybierz nothing, a następnie skopiować lub wyciąć.  
  
-   Po wybraniu tej opcji pusty wiersz jest skopiować lub wyciąć. Jeśli następnie wkleić, jest wstawiany nowy, pusty wiersz.  
  
-   Gdy ta opcja jest wyczyszczone, polecenie Cut usuwa pustych wierszy. Jednak dane w Schowku jest zachowywana. W związku z tym Jeśli następnie użyć polecenia Wklej, zostanie wklejony zawartości ostatnio skopiowana do Schowka. Jeśli nic nie został skopiowany wcześniej, nic nie zostanie wklejony.  
  
 To ustawienie nie ma wpływu na Kopiuj lub Wytnij gdy wiersz nie jest pusty. Jeśli nic nie jest zaznaczone, cały wiersz jest skopiować lub wyciąć. Jeśli następnie wkleić, tekst cały wiersz i jej znak endline zostaną wklejone.  
  
> [!TIP]
>  Aby wyświetlić wskaźniki dla miejsca do magazynowania oraz o końców linii, a zatem odróżnienia wiersze z wcięciami wiersze, które są całkowicie pusty, wybierz **zaawansowane** z **Edytuj** menu i wybierz polecenie **widoku biały Miejsce**.  
  
## <a name="display"></a>Monitor  
 Numery wierszy  
 Po wybraniu numer wiersza obok każdego wiersza kodu.  
  
> [!NOTE]
>  Te numery wierszy nie są dodawane do kodu, a nie do drukowania. Są one tylko do celów referencyjnych.  
  
 Włącz nawigację adresów URL jednym kliknięciem  
 Po wybraniu myszy przybiera postać dłoni przekazywanego za pośrednictwem adresu URL w edytorze. Możesz kliknąć adres URL, aby wyświetlić stronę wskazany w przeglądarce sieci Web.  
  
 Pasek nawigacyjny  
 Po wybraniu Wyświetla **pasek nawigacyjny** w górnej części edytora kodu. Jego listy rozwijanej **obiektów** i **członków** list pozwalają na wybranie określonego obiektu w kodzie, wybierz jedną z jej członków i przechodzi do deklaracji wybranego elementu członkowskiego w edytorze kodu.  
  
## <a name="see-also"></a>Zobacz też  
 [Opcje, Edytor tekstu, wszystkie języki, karty](../../ide/reference/options-text-editor-all-languages-tabs.md)   
 [Ogólne, środowisko, okno dialogowe Opcje](../../ide/reference/general-environment-options-dialog-box.md)   
 [Korzystanie z funkcji IntelliSense](../../ide/using-intellisense.md)



