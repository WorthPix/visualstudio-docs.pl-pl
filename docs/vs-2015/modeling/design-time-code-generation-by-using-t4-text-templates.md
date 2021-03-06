---
title: Generowanie kodu czasu projektowania przy użyciu szablonów tekstowych T4 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, guidelines for code generation
- text templates, data source model
- TextTemplatingFileGenerator custom tool
- Transform All Templates
- text templates, getting started
- Text Template project item
- text templates, generating code for your application
ms.assetid: 2774b83d-1adb-4c66-a607-746e019b80c0
caps.latest.revision: 40
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 1edc6e7d66e8b371f38e16052ba26fa61287e398
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49268336"
---
# <a name="design-time-code-generation-by-using-t4-text-templates"></a>Generowanie kodu czasu projektowania przy użyciu szablonów tekstowych T4
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Szablony tekstowe T4 projektowania umożliwiają generowanie kodu programu i innych plików w Twojej [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projektu. Zazwyczaj piszesz szablony, dzięki czemu mogą się różnić kodu, które generują zgodnie z danymi z *modelu*. Model jest pliku lub bazy danych, który zawiera najważniejsze informacje o wymaganiach dotyczących aplikacji.  
  
 Na przykład można mieć modelu, który definiuje przepływ pracy, jako tabelę lub diagram. Z modelu można wygenerować oprogramowania, który wykonuje przepływ pracy. Gdy zmienią się wymagania użytkowników, jest łatwa w celu omówienia nowy przepływ pracy z użytkownikami. Ponowne generowanie kodu z przepływu pracy jest bardziej niezawodną metodą od ręcznego aktualizowania kodu.  
  
> [!NOTE]
>  A *modelu* jest źródłem danych, który opisuje danego aspekt aplikacji. Może być każdym formularzu, dowolny rodzaj pliku lub bazy danych. Nie musi znajdować się w dowolnym danego formularza, takie jak modelu UML lub model języka specyficznego dla domeny. Typowe są modele w formie tabel lub plików XML.  
  
 Prawdopodobnie znasz generowania kodu. Podczas definiowania zasobów w **resx** plików w Twojej [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozwiązania, zestaw klas i metod jest generowana automatycznie. Plik zasobów umożliwia łatwiejsze i bardziej niezawodny, aby edytować zasoby niż byłaby, jeśli trzeba było edytować klasy i metody. Przy użyciu szablonów tekstowych może wygenerować kod w taki sam sposób, ze źródła własnego projektu.  
  
 Szablon tekstu zawiera tekst, który ma zostać wygenerowany i kod programu, który generuje zmiennej fragmenty tekstu. Kod programu i umożliwia Powtórz lub warunkowo pominięcie części wygenerowanego tekstu. Wygenerowany tekst może sam się kod programu, który będzie stanowić część aplikacji.  
  
## <a name="creating-a-design-time-t4-text-template"></a>Tworzenie szablonów tekstowych T4 w czasie projektowania  
  
#### <a name="to-create-a-design-time-t4-template-in-visual-studio"></a>Aby utworzyć szablon T4 czasu projektowania w programie Visual Studio  
  
1.  Utwórz [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projektu lub Otwórz istniejący.  
  
     Na przykład na **pliku** menu, wybierz **New**, **projektu**.  
  
2.  Dodaj plik szablonu tekstu do projektu i nadaj jej nazwę, który ma rozszerzenie **.tt**.  
  
     Aby to zrobić, w **Eksploratora rozwiązań**, w menu skrótów projektu wybierz **Dodaj**, **nowy element**. W **Dodaj nowy element** wybierz okno dialogowe **szablon tekstowy** ze środkowego okienka.  
  
     Należy zauważyć, że **narzędzie niestandardowe** właściwości pliku **TextTemplatingFileGenerator**.  
  
3.  Otwórz plik. Będzie już zawierać następujące dyrektywy:  
  
    ```  
    <#@ template hostspecific="false" language="C#" #>  
    <#@ output extension=".txt" #>  
    ```  
  
     Jeśli dodano szablon, aby [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] projekt, będzie atrybut language "`VB`".  
  
4.  Dodaj jakiś tekst na końcu pliku. Na przykład:  
  
    ```  
    Hello, world!  
    ```  
  
5.  Zapisz plik.  
  
     Może zostać wyświetlony **ostrzeżenie o zabezpieczeniach** okno komunikatu, które wyświetli monit o potwierdzenie, że chcesz uruchomić szablon. Kliknij przycisk **OK**.  
  
6.  W **Eksploratora rozwiązań**, rozwiń węzeł pliku szablonu, a plik, który ma rozszerzenie **.txt**. Plik zawiera wygenerowane z szablonu.  
  
    > [!NOTE]
    >  Jeśli projekt jest projekt języka Visual Basic, należy kliknąć przycisk **Pokaż wszystkie pliki** aby można było wyświetlić plik wyjściowy.  
  
### <a name="regenerating-the-code"></a>Trwa ponowne generowanie kodu  
 Szablon zostanie wykonana, generowanie plików pomocniczych, w dowolnym z następujących przypadkach:  
  
-   Edytowanie szablonu, a następnie zmień fokus na inne [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] okna.  
  
-   Zapisz szablon.  
  
-   Kliknij przycisk **Przekształć wszystkie szablony** w **kompilacji** menu. To spowoduje przekształcenie wszystkie szablony w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozwiązania.  
  
-   W **Eksploratora rozwiązań**menu skrótów w dowolnych plików, wybierz **Uruchom narzędzie niestandardowe**. Ta metoda umożliwia przekształcanie podzbiór wybranych szablonów.  
  
 Możesz również skonfigurować [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projektu, dzięki czemu szablony są wykonywane, gdy zostały zmienione pliki danych, które będzie ją odczytać. Aby uzyskać więcej informacji, zobacz [ponowne generowanie kodu automatycznie](#Regenerating).  
  
## <a name="generating-variable-text"></a>Generowanie tekstu o zmiennym  
 Szablony tekstowe umożliwiają używanie kodu programu do zmiany zawartości w wygenerowanym pliku.  
  
#### <a name="to-generate-text-by-using-program-code"></a>Aby wygenerować tekst przy użyciu kodu programu  
  
1.  Zmień zawartość `.tt` pliku:  
  
    ```csharp  
    <#@ template hostspecific="false" language="C#" #>  
    <#@ output extension=".txt" #>  
    <#int top = 10;  
  
    for (int i = 0; i<=top; i++)   
    { #>  
       The square of <#= i #> is <#= i*i #>  
    <# } #>  
    ```  
  
    ```vb  
    <#@ template hostspecific="false" language="VB" #>  
    <#@ output extension=".txt" #>  
    <#Dim top As Integer = 10  
  
    For i As Integer = 0 To top  
    #>  
        The square of <#= i #> is <#= i*i #>  
    <#  
    Next  
    #>  
  
    ```  
  
2.  Zapisz plik .tt i sprawdź plik txt wygenerowane ponownie. Wyświetla listę kwadratów liczb z zakresu od 0 do 10.  
  
 Należy zauważyć, że instrukcje są ujęte w `<#...#>`i jednego wyrażenia w `<#=...#>`. Aby uzyskać więcej informacji, zobacz [pisanie szablonu tekstowego T4](../modeling/writing-a-t4-text-template.md).  
  
 Jeśli piszesz kod [!INCLUDE[vbprvb](../includes/vbprvb-md.md)], `template` dyrektywy powinien zawierać `language="VB"`. `"C#"` jest ustawieniem domyślnym.  
  
## <a name="debugging-a-design-time-t4-text-template"></a>Debugowanie szablonu tekstowego T4 w czasie projektowania  
 Debugowanie szablonu tekstowego:  
  
-   Wstaw `debug="true"` do `template` dyrektywy. Na przykład:  
  
     `<#@ template debug="true" hostspecific="false" language="C#" #>`  
  
-   Ustaw punkty przerwania w szablonie, w taki sam sposób jak w przypadku zwykłego kodu.  
  
-   Wybierz **Debuguj szablon T4** przejdź do menu skrótów w pliku szablonu tekstu w oknie Eksploratora rozwiązań.  
  
 Szablon ma uruchamiać i zatrzymywał w punktach przerwania. Można zbadać zmienne i przejść przez kod w zwykły sposób.  
  
> [!TIP]
>  `debug="true"` sprawia, że wygenerowany kod mapowania dokładniej szablonu tekstu, wstawiając więcej dyrektywy numerację wierszy w wygenerowanym kodzie. Pozostawienie go punktów przerwania może spowodować zatrzymanie wykonywania w nieodpowiednim stanie.  
>   
>  Ale nawet wtedy, gdy nie jest debugowany, można pozostawić klauzuli w dyrektywie szablonu. Powoduje to bardzo mały spadek wydajności.  
  
## <a name="generating-code-or-resources-for-your-solution"></a>Generowanie kodu lub zasobów dla rozwiązania  
 Można wygenerować pliki programów, które różnią się w zależności od tego modelu. Model jest wartością wejściową, takich jak bazy danych, pliku konfiguracji, modelu UML, modelu DSL lub innego źródła. Możesz wygenerować zazwyczaj kilka plików programów pochodzą z tego samego modelu. Aby to osiągnąć, Utwórz plik szablonu dla każdego pliku wygenerowanego programu, a wszystkie szablony po ich przeczytaniu tego samego modelu.  
  
#### <a name="to-generate-program-code-or-resources"></a>Aby wygenerować kod programu lub zasobów  
  
1.  Zmień dyrektywie wyjścia, aby wygenerować plik odpowiedniego typu, takich jak CS, .vb, resx lub XML.  
  
2.  Wstaw kod, który zostanie wygenerowany kod rozwiązania, która jest wymagana. Na przykład, jeśli chcesz wygenerować trzy deklaracje pola Liczba całkowita w klasie:  
  
    ```csharp  
  
              <#@ template debug="false" hostspecific="false" language="C#" #>  
    <#@ output extension=".cs" #>  
    <# var properties = new string [] {"P1", "P2", "P3"}; #>  
    // This is generated code:  
    class MyGeneratedClass {  
    <# // This code runs in the text template:  
      foreach (string propertyName in properties)  { #>  
      // Generated code:  
      private int <#= propertyName #> = 0;  
    <# } #>  
    }  
    ```  
  
    ```vb  
    <#@ template debug="false" hostspecific="false" language="VB" #>  
    <#@ output extension=".cs" #>  
    <# Dim properties = {"P1", "P2", "P3"} #>  
    class MyGeneratedClass {  
    <#   
       For Each propertyName As String In properties  
    #>  
      private int <#= propertyName #> = 0;  
    <#  
       Next  
    #>  
    }  
  
    ```  
  
3.  Zapisz plik i sprawdzić wygenerowanego pliku, który zawiera teraz następujący kod:  
  
    ```  
    class MyGeneratedClass {  
      private int P1 = 0;   
      private int P2 = 0;  
      private int P3 = 0;  
    }  
    ```  
  
### <a name="generating-code-and-generated-text"></a>Generowanie kodu i wygenerowanego tekstu  
 Podczas generowania kodu programu jest najważniejsza uniknąć mylące generowania kodu, który jest wykonywany w szablonie, a wynikowy wygenerowany kod, który będzie częścią rozwiązania. Te dwa języki ma być takie same.  
  
 Poprzedni przykład zawiera dwie wersje. W jednej wersji generowania kodu jest w języku C#. W innych wersjach generowania kodu jest języka Visual Basic. Ale tekst generowany przez obie z nich jest taki sam, a to klasa C#.  
  
 W ten sam sposób, można użyć [!INCLUDE[csprcs](../includes/csprcs-md.md)] szablonu, aby wygenerować kod w dowolnym języku. Wygenerowanego tekstu nie musi być w dowolnym języku określonego i nie musi być kodu programu.  
  
### <a name="structuring-text-templates"></a>Tworzenie struktury szablonów tekstowych  
 Jako dobrą praktyką dążymy do oddzielania kod szablonu na dwie części:  
  
-   Konfiguracja lub część gromadzenia danych, która ustawia wartości w zmiennych, ale nie zawiera bloki tekstu. W poprzednim przykładzie, ta część jest zainicjowanie `properties`.  
  
     Jest to czasem nazywane sekcji "model", ponieważ tworzy model w sklepie i zazwyczaj odczytuje plik modelu.  
  
-   Generowanie tekstu części (`foreach(...){...}` w przykładzie), który używa wartości zmiennych.  
  
 To nie jest konieczne separacji, ale jest styl, dzięki czemu łatwiej odczytać szablonu, co zmniejsza złożoność part, który zawiera tekst.  
  
## <a name="reading-files-or-other-sources"></a>Odczytywanie plików lub innych źródeł  
 Aby uzyskać dostęp do pliku modelu lub bazy danych, kod szablonu użyć zestawy, takie jak System.XML. Aby uzyskać dostęp do tych zestawów, należy wstawić dyrektyw, takich jak te:  
  
```  
<#@ assembly name="System.Xml.dll" #>  
<#@ import namespace="System.Xml" #>  
<#@ import namespace="System.IO" #>  
```  
  
 `assembly` Dyrektywy udostępnia określony zestaw kod szablonu w taki sam sposób jak sekcję odwołania [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projektu. Nie musisz dołączyć odwołanie do System.dll, który odwołuje się automatycznie. `import` Dyrektywy pozwala na używanie typów bez używania ich w pełni kwalifikowane nazwy w taki sam sposób jak `using` dyrektywy w pliku zwykłego programu.  
  
 Na przykład po zaimportowaniu **System.IO**, można napisać:  
  
```csharp  
  
      <# var properties = File.ReadLines("C:\\propertyList.txt");#>  
...  
<# foreach (string propertyName in properties) { #>  
...  
```  
  
```vb  
<# For Each propertyName As String In   
             File.ReadLines("C:\\propertyList.txt")  
#>  
  
```  
  
### <a name="opening-a-file-with-a-relative-pathname"></a>Otwieranie pliku względną nazwę ścieżki  
 Aby załadować plik z lokalizacji względnej wobec szablonu tekstu, można użyć `this.Host.ResolvePath()`. Aby użyć tej opcji. Host, należy ustawić `hostspecific="true"` w `template`:  
  
```  
<#@ template debug="false" hostspecific="true" language="C#" #>  
  
```  
  
 Następnie można napisać, na przykład:  
  
```csharp  
<# string fileName = this.Host.ResolvePath("filename.txt");  
  string [] properties = File.ReadLines(filename);  
#>  
...  
<#  foreach (string propertyName in properties { #>  
...  
  
```  
  
```vb  
<# Dim fileName = Me.Host.ResolvePath("propertyList.txt")  
   Dim properties = File.ReadLines(filename)  
#>  
...  
<#   For Each propertyName As String In properties  
...  
#>  
  
```  
  
 Można również użyć `this.Host.TemplateFile`, który identyfikuje nazwę bieżącego pliku szablonu.  
  
 Typ `this.Host` (w języku Visual Basic, `Me.Host`) jest `Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost`.  
  
### <a name="getting-data-from-includevsprvsincludesvsprvs-mdmd"></a>Pobieranie danych z [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]  
 Do korzystania z usług w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]ustaw `hostSpecific` atrybut i obciążenia `EnvDTE` zestawu. Można następnie użyć IServiceProvider.GetCOMService() dostęp do obiektu DTE i innych usług. Na przykład:  
  
```scr  
<#@ template hostspecific="true" language="C#" #>  
<#@ output extension=".txt" #>  
<#@ assembly name="EnvDTE" #>  
<#  
  IServiceProvider serviceProvider = (IServiceProvider)this.Host;  
  EnvDTE.DTE dte = (EnvDTE.DTE) serviceProvider.GetCOMService(typeof(EnvDTE.DTE));  
#>  
  
Number of projects in this VS solution:  <#= dte.Solution.Projects.Count #>  
  
```  
  
> [!TIP]
>  Szablon tekstowy, który jest uruchamiany w domenie aplikacji i usług używanych przez kierowanie. W takiej sytuacji GetCOMService() jest bardziej niezawodną metodą od GetService().  
  
##  <a name="Regenerating"></a> Automatyczne ponowne generowanie kodu  
 Zazwyczaj kilka plików w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozwiązania są generowane przy użyciu jednego modelu danych wejściowych. Każdy plik jest generowany na podstawie własnego szablonu, ale szablony, które wszystkie odnoszą się do tego samego modelu.  
  
 Jeśli zmieni się w modelu źródłowym, należy ponownie uruchom wszystkie szablony w rozwiązaniu. Aby to zrobić ręcznie, wybierz opcję **Przekształć wszystkie szablony** na **kompilacji** menu.  
  
 Jeśli zainstalowano [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] wizualizacji i modelowania SDK może mieć wszystkie szablony, które są przekształcane automatycznie zawsze wtedy, gdy wykonujesz kompilację. Aby to zrobić, Edytuj plik projektu (.csproj lub .vbproj) w edytorze tekstów i dodaj następujące wiersze w pobliżu końca pliku, po innych `<import>` instrukcji:  
  
```  
<Import Project="$(MSBuildExtensionsPath)\Microsoft\VisualStudio\v11.0\TextTemplating\Microsoft.TextTemplating.targets" />  
<PropertyGroup>  
   <TransformOnBuild>true</TransformOnBuild>  
   <!-- Other properties can be inserted here -->  
</PropertyGroup>  
```  
  
 Aby uzyskać więcej informacji, zobacz [generowanie kodu w procesie kompilacji](../modeling/code-generation-in-a-build-process.md).  
  
## <a name="error-reporting"></a>Raportowanie błędów  
 Aby umieścić błędów i komunikaty ostrzegawcze w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] oknie błędów, można użyć następujących metod:  
  
```  
Error("An error message");  
Warning("A warning message");  
```  
  
##  <a name="Converting"></a> Konwertowanie istniejącego pliku do szablonu  
 Przydatną cechą szablony to, że wyglądają bardzo podobnie pliki, które generują, wraz z kodu programu wstawiono. Sugeruje to przydatny sposób tworzenia szablonu. Należy najpierw utworzyć zwykły plik jako prototyp, takich jak [!INCLUDE[csprcs](../includes/csprcs-md.md)] pliku i stopniowo wprowadzenie kodu generowania, który jest różny wynikowy plik.  
  
#### <a name="to-convert-an-existing-file-to-a-design-time-template"></a>Aby przekonwertować szablon czasu projektowania istniejącego pliku  
  
1.  Do Twojej [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projektu, Dodaj plik typu, który chcesz wygenerować, takich jak `.cs`, `.vb`, lub `.resx` pliku.  
  
2.  Przetestuj nowy plik, aby upewnić się, że działa.  
  
3.  W Eksploratorze rozwiązań, zmień rozszerzenie nazwy pliku **.tt**.  
  
4.  Sprawdź następujące właściwości **.tt** pliku:  
  
    |||  
    |-|-|  
    |**Niestandardowe narzędzie =**|**TextTemplatingFileGenerator**|  
    |**Akcja kompilacji =**|**Brak**|  
  
5.  Wstaw następujące wiersze na początku pliku:  
  
    ```  
    <#@ template debug="false" hostspecific="false" language="C#" #>  
    <#@ output extension=".cs" #>  
    ```  
  
     Jeśli chcesz napisać kod szablonu w [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]ustaw `language` atrybutu `"VB"` zamiast `"C#"`.  
  
     Ustaw `extension` atrybutu rozszerzenie nazwy pliku dla typu pliku, który chcesz wygenerować, na przykład `.cs`, `.resx`, lub `.xml`.  
  
6.  Zapisz plik.  
  
     Pomocniczy tworzony jest plik, z określonym rozszerzeniem. Jego właściwości są odpowiednie dla typu pliku. Na przykład **Build Action** będzie właściwości pliku CS **skompilować**.  
  
     Sprawdź, czy wygenerowany plik zawiera tę samą zawartość, jak oryginalny plik.  
  
7.  Określ część pliku, którego chcesz się różnić. Na przykład element, który pojawia się tylko w określonych warunkach lub części, która jest powtórzona lub gdzie określone wartości różnią się. Wstaw generowania kodu. Zapisz plik i sprawdzić, czy poprawnie generowany jest plik pomocniczy. Powtórz ten krok.  
  
## <a name="guidelines-for-code-generation"></a>Wskazówki dotyczące generowania kodu  
 Zobacz [wytyczne dotyczące szablonów tekstowych T4 pisania](../modeling/guidelines-for-writing-t4-text-templates.md).  
  
## <a name="next-steps"></a>Następne kroki  
  
|Następny krok|Temat|  
|---------------|-----------|  
|Twórz i Debuguj bardziej zaawansowanych szablonu tekstu, z kodem, który korzysta z funkcji pomocniczych, dołączone pliki i dane zewnętrzne.|[Pisanie szablonu tekstowego T4](../modeling/writing-a-t4-text-template.md)|  
|Generowanie dokumentów przy użyciu szablonów w czasie wykonywania.|[Generowanie tekstu czasu wykonywania przy użyciu szablonów tekstowych T4](../modeling/run-time-text-generation-with-t4-text-templates.md)|  
|Generowanie tekstu poza Uruchom [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].|[Generowanie plików za pomocą narzędzia TextTransform](../modeling/generating-files-with-the-texttransform-utility.md)|  
|Przekształć dane w postaci języka specyficznego dla domeny.|[Generowanie kodu z języka specyficznego dla domeny](../modeling/generating-code-from-a-domain-specific-language.md)|  
|Napisz dyrektywy procesorów, którą należy przekształcić źródła danych.|[Dopasowanie przekształcenia tekstu T4](../modeling/customizing-t4-text-transformation.md)|  
  
## <a name="see-also"></a>Zobacz też  
 [Zalecenia dotyczące pisania szablonów tekstowych T4](../modeling/guidelines-for-writing-t4-text-templates.md)



