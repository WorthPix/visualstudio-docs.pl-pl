---
title: Tworzenie aplikacji z natywnym interfejsem użytkownika przy użyciu platformy Xamarin w programie Visual Studio | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 03/30/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 30f137e6-595d-4ce7-b8f5-415b07c1caa2
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: b68dd62de137e3c9427715c647ba4a53f07bd281
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/20/2018
ms.locfileid: "46496158"
---
# <a name="build-apps-with-native-ui-using-xamarin-in-visual-studio"></a>Tworzenie aplikacji za pomocą natywnego interfejsu użytkownika przy użyciu platformy Xamarin w programie Visual Studio

Większość programistów, którzy zdecydowali środowiska Xamarin i C# do tworzenia aplikacji mobilnych dla wielu platform przy użyciu formularzy Xamarin.Forms. Zestaw narzędzi Xamarin.Forms definiuje interfejs użytkownika, który jest mapowany do kontrolki natywne w systemie iOS, Android i uniwersalnej platformy Windows (UWP). Zestaw narzędzi Xamarin.Forms jest opisany w artykule [opanowaniu podstaw tworzenia aplikacji przy użyciu zestawu narzędzi Xamarin.Forms w programie Visual Studio](learn-app-building-basics-with-xamarin-forms-in-visual-studio.md).

W tym artykule opisano różne podejście, która obejmuje dostęp do interfejsów API natywnego interfejsu użytkownika dla każdej platformy. Praca z natywnych interfejsów API jest dużo trudniejsze podejścia, niż zestawu narzędzi Xamarin.Forms, ponieważ wymaga obszerną wiedzę na temat każdej z platform. Zaletą jest to, czy można dostosować interfejs użytkownika do szczególne zalety i możliwości każdej z tych platform nadal współużytkując podstawowej logiki biznesowej.

Po wykonaniu kroków [Instalator i instalacja](../cross-platform/setup-and-install.md) i [Sprawdź swoje środowisko Xamarin](../cross-platform/verify-your-xamarin-environment.md), w tym instruktażu dowiesz się, jak utworzyć podstawową aplikację Xamarin z natywnych warstwy interfejsu użytkownika. Z natywnym interfejsem użytkownika udostępnionego kodu znajduje się w bibliotece programu .NET Standard i projekty poszczególnych platform zawierają definicje interfejsu użytkownika. Poniżej przedstawiono aplikację, którą utworzysz systemem (od lewej do prawej) dla systemu iOS i telefony z systemem Android i Windows 10 desktop.

![Aplikacja Xamarin w systemach iOS, Android i Windows](../cross-platform/media/cross-plat-xamarin-build-1-Large.png#lightbox)

Wykonasz te czynności na tworzenie:

- [Konfigurowanie rozwiązania programu](#solution)

- [Pisanie kodu usług udostępnionych danych](#dataservice)

- [Projektowanie interfejsu użytkownika dla systemu Android](#Android)

- [Projektowanie interfejsu użytkownika dla Windows](#Windows)

- [Następne kroki](#next), który obejmuje projektowanie interfejsu użytkownika dla systemu iOS

> [!TIP]
> Możesz znaleźć pełnego kodu źródłowego dla tego projektu w [mobile-samples repository w witrynie GitHub](https://github.com/xamarin/mobile-samples/tree/master/Weather).
>
> Jeśli masz trudności lub występują błędy, Opublikuj pytania na [forums.xamarin.com](http://forums.xamarin.com). Wiele błędów, które można rozwiązać, aktualizując do najnowsze zestawy SDK wymagane przez środowisko Xamarin, które są opisane w [informacje o wersji platformy Xamarin](https://developer.xamarin.com/releases/) dla każdej platformy.

> [!NOTE]
> Dokumentacja dla deweloperów platformy Xamarin oferuje również kilka przewodników z sekcjami Szybki Start i szczegółowe informacje wymienione poniżej. Na tych stronach upewnij się, że wybrano "Visual Studio", aby wyświetlić wskazówki specyficzne dla programu Visual Studio.
>
>  -   Aplikacje platformy Xamarin z natywnym interfejsem użytkownika:
>     -   [Witaj, Android](/xamarin/android/get-started/hello-android/) (prosta aplikacja z jednym ekranem)
>     -   [Witaj, Android (wiele ekranów)](/xamarin/android/get-started/hello-android-multiscreen/) (aplikacja z nawigacją między ekranami)
>     -   [Dla systemu android przewodnik fragmenty](/xamarin/android/platform/fragments/implementing-with-fragments/) (używane dla rekordu głównego/szczegółów ekranów, między innymi)
>     -   [Witaj, iOS](/xamarin/ios/get-started/hello-iOS/)
>     -   [Witaj, iOS Multiscreen (wiele ekranów)](/xamarin/ios/get-started/hello-iOS-multiscreen/)

>  -   Aplikacje Xamarin przy użyciu zestawu narzędzi Xamarin.Forms (współdzielony interfejs użytkownika)
>     -   [Witaj, Xamarin.Forms](/xamarin/xamarin-forms/get-started/hello-xamarin-forms/quickstart/)
>     -   [Witaj, Xamarin.Forms (wiele ekranów)](/xamarin/xamarin-forms/get-started/hello-xamarin-forms-multiscreen/)

<a name="solution" />

##  <a name="set-up-your-solution"></a>Konfigurowanie rozwiązania programu

Program Visual Studio nie ma szablonu rozwiązania do tworzenia natywnych aplikacji interfejsu użytkownika, udostępnianie biblioteki .NET Standard. Jednak nie jest trudne do kompilowania rozwiązania z indywidualnymi projektami. Te kroki służą utworzeniu rozwiązania Xamarin z projektami dla każdego typu aplikacji platformy i biblioteki .NET Standard dla udostępnionego kodu.

1.  W programie Visual Studio Utwórz nowy **biblioteki klas (.NET Standard)** rozwiązania i nadaj mu nazwę **WeatherApp**. Można znaleźć ten szablon najłatwiej, wybierając **Visual C#** po lewej stronie i następnie **.NET Standard**:

    ![Tworzenie rozwiązań .NET Standard](../cross-platform/media/cross-plat-xamarin-build-2.png)

    Po kliknięciu przycisku OK, **WeatherApp** rozwiązanie składa się z pojedynczego projektu o nazwie **WeatherApp**.

2.  Jeśli chcesz docelowy z systemem iOS, należy dodać projektu systemu iOS do rozwiązania. Kliknij prawym przyciskiem myszy nazwę rozwiązania w **Eksploratora rozwiązań** i wybierz **Dodaj** i **nowy projekt**.  W **nowy projekt** okno dialogowe, w polu po lewej stronie wybierz **Visual C#**, a następnie **iOS** i **Universal**. (Jeśli tak nie jest dostępne, może być konieczne instalacji Xamarin lub włączyć funkcję Visual Studio 2017, zobacz [Instalator i instalacja](../cross-platform/setup-and-install.md).) Na liście szablonów wybierz **aplikacja pojedynczego widoku (iOS)**. Nadaj mu nazwę **WeatherApp.iOS**.

3.  Jeśli ma pod kątem systemów Android, należy dodać projekt systemu Android w rozwiązaniu. W **nowy projekt** okno dialogowe, w polu po lewej stronie wybierz **Visual C#** i **Android**. Na liście szablonów wybierz **pusta aplikacja (Android)**. Nadaj mu nazwę **WeatherApp.Android**.

4. Jeśli chcesz przeanalizować platformie Universal Windows w **nowy projekt** okno dialogowe, w polu po lewej stronie wybierz **Visual C#** i **Windows Universal**. Na liście szablonów wybierz **pusta aplikacja (Windows Universal)** i nadaj mu nazwę **WeatherApp.UWP**.

5. Dla każdej aplikacji projektów (iOS, Android i platformy uniwersalnej systemu Windows), kliknij prawym przyciskiem myszy **odwołania** sekcji **Eksploratora rozwiązań** i wybierz **Dodaj odwołanie**. W **Menadżer odwołań** okno dialogowe, w polu po lewej stronie wybierz **projektu** i **rozwiązania**. Zobaczysz listę wszystkich projektów w rozwiązaniu, z wyjątkiem projektu odwołania, którego zarządzasz:

   ![Ustawianie odwołań do projektu .NET Standard](../cross-platform/media/cross-plat-xamarin-build-3.png)

   Zaznacz pole wyboru obok pozycji **WeatherApp**.

   Po sprawdzeniu tego pola dla każdego z projektów aplikacji, wszystkie projekty zawierają odwołania do biblioteki .NET Standard i mogą współużytkować kod w tej bibliotece.

6. Dodaj **Newtonsoft.Json** pakiet NuGet do projektu .NET Standard, który zostanie użyty do przetwarzania informacji pobrane z usługi danych o pogodzie:

    -   Kliknij prawym przyciskiem myszy **WeatherApp** projektu w **Eksploratora rozwiązań** i wybierz **Zarządzaj pakietami NuGet...** .

         W oknie NuGet wybierz **Przeglądaj** kartę i wyszukaj **Newtonsoft**.

    -   Wybierz **Newtonsoft.Json**.

    -   Upewnij się, **wersji** pole jest ustawione na **najnowszy stabilny** wersji.

    -   Kliknij przycisk **zainstalować**.

7.  Powtórz krok 6, aby znaleźć i zainstalować **Microsoft.CSharp** pakiet w projekcie .NET Standard. Ta biblioteka jest niezbędne do korzystania z języka C# `dynamic` danych wpisz biblioteki .NET Standard.

8.  Skompiluj rozwiązanie i upewnij się, że żadne błędy kompilacji.

<a name="dataservice" />

## <a name="write-shared-data-service-code"></a>Pisanie kodu usług udostępnionych danych

 **WeatherApp** projekt jest biblioteki .NET Standard. Ten projekt jest, gdzie Ty napiszesz kod, który jest udostępniany na wszystkich platformach. Ponieważ każdy projekt aplikacji ma odwołanie do biblioteki .NET Standard, biblioteka jest dołączony do systemów iOS, Android i platformy uniwersalnej systemu Windows pakietów aplikacji.

 Poniższe kroki Dodaj kod do biblioteki .NET Standard do przechowywania danych z tej usługi pogody i dostęp do:

1.  Najpierw Załóż bezpłatne pogody klucz interfejsu API w [ http://openweathermap.org/appid ](http://openweathermap.org/appid). Ten klucz interfejsu API umożliwi aplikacji, aby uzyskać dane pogody dla dowolnego kodu pocztowego w Stanach Zjednoczonych. (Działa dla kodów pocztowych poza Stanami Zjednoczonymi.)

2.  Kliknij prawym przyciskiem myszy **WeatherApp** projektu, a następnie wybierz **Dodaj > klasa...** . W **Dodaj nowy element** okno dialogowe, nazwij plik *Weather.cs*. Ta klasa będzie używane do przechowywania danych z usługi danych o pogodzie.

3.  Zastąp całą zawartość *Weather.cs* następującym kodem:

    ```csharp
    namespace WeatherApp
    {
        public class Weather
        {
            // Because labels bind to these values, set them to an empty string to
            // ensure that the label appears on all platforms by default.
            public string Title { get; set; } = " ";
            public string Temperature { get; set; } = " ";
            public string Wind { get; set; } = " ";
            public string Humidity { get; set; } = " ";
            public string Visibility { get; set; } = " ";
            public string Sunrise { get; set; } = " ";
            public string Sunset { get; set; } = " ";
        }
    }
    ```

4.  Dodaj klasę do projektu .NET Standard, o nazwie `DataService.cs`. Użyjesz tej klasy do przetwarzania danych JSON z usługi danych o pogodzie.

5.  Zastąp całą zawartość *DataService.cs* następującym kodem:

    ```csharp
    using System.Net.Http;
    using System.Threading.Tasks;
    using Newtonsoft.Json;

    namespace WeatherApp
    {
        public class DataService
        {
            public static async Task<dynamic> GetDataFromService(string queryString)
            {
                HttpClient client = new HttpClient();
                var response = await client.GetAsync(queryString);

                dynamic data = null;
                if (response != null)
                {
                    string json = response.Content.ReadAsStringAsync().Result;
                    data = JsonConvert.DeserializeObject(json);
                }

                return data;
            }
        }
    }
    ```

6.  Dodaj klasę innych do biblioteki .NET Standard, o nazwie *Core.cs*. Klasa będzie używana do formę ciągu zapytania za pomocą kod pocztowy, wywołania usługi danych o pogodzie i wypełniania wystąpienia **pogody** klasy.

7.  Zastąp zawartość *Core.cs* następującym kodem:

    ```csharp
    using System;
    using System.Threading.Tasks;

    namespace WeatherApp
    {
        public class Core
        {
            public static async Task<Weather> GetWeather(string zipCode)
            {
                //Sign up for a free API key at http://openweathermap.org/appid
                string key = "YOUR API KEY HERE";
                string queryString = "http://api.openweathermap.org/data/2.5/weather?zip="
                    + zipCode + ",us&appid=" + key + "&units=imperial";

                //Make sure developers running this sample replaced the API key
                if (key == "YOUR API KEY HERE")
                {
                    throw new ArgumentException("You must obtain an API key from openweathermap.org/appid and save it in the 'key' variable.");
                }

                dynamic results = await DataService.GetDataFromService(queryString).ConfigureAwait(false);

                if (results["weather"] != null)
                {
                    Weather weather = new Weather();
                    weather.Title = (string)results["name"];
                    weather.Temperature = (string)results["main"]["temp"] + " F";
                    weather.Wind = (string)results["wind"]["speed"] + " mph";
                    weather.Humidity = (string)results["main"]["humidity"] + " %";
                    weather.Visibility = (string)results["weather"][0]["main"];

                    DateTime time = new System.DateTime(1970, 1, 1, 0, 0, 0, 0);
                    DateTime sunrise = time.AddSeconds((double)results["sys"]["sunrise"]);
                    DateTime sunset = time.AddSeconds((double)results["sys"]["sunset"]);
                    weather.Sunrise = sunrise.ToString() + " UTC";
                    weather.Sunset = sunset.ToString() + " UTC";
                    return weather;
                }
                else
                {
                    return null;
                }
            }
        }
    }
    ```

8. Zamień na pierwsze wystąpienie *tutaj klucz interfejsu API usługi* przy użyciu klucza interfejsu API, uzyskane w kroku 1. Nadal wymaga ją w cudzysłowie!

9. Usuń *MyClass.cs* biblioteki .NET Standard, ponieważ nie będą używane.

10. Tworzenie **WeatherApp** projekt, aby upewnić się, czy kod jest poprawny.

<a name="Android" />

## <a name="design-ui-for-android"></a>Projektowanie interfejsu użytkownika dla systemu Android

 Teraz możesz projektować interfejs użytkownika, połącz go ze współużytkowanym kodem, a następnie uruchom aplikację.

### <a name="design-the-look-and-feel-of-your-app"></a>Projektowanie wyglądu i działania aplikacji

1.  W **Eksploratora rozwiązań**, rozwiń węzeł **WeatherApp.Droid > Zasoby > układ** folder i Otwórz *Main.axml*. To polecenie otwiera plik w Projektancie visual. (Jeśli pojawi się błąd, który języka Java, zobacz ten [wpis w blogu](http://forums.xamarin.com/discussion/32365/connection-to-the-layout-renderer-failed-in-xs-5-7-and-xamarinvs-3-9).)

    > [!TIP]
    >  Istnieją inne pliki w projekcie. Eksplorowanie ich jest poza zakres tego artykułu, ale jeśli chcesz od razu do struktury projektu dla systemu Android nieco więcej, zobacz [szczegółowe dane w części 2](/xamarin/android/get-started/hello-android/hello-android-deepdive/) artykułu Hello systemu Android.

2.  Otwórz przybornika **Widok > inne Windows > przybornika**.

3.  Z **przybornika**, przeciągnij **RelativeLayout** formant do projektanta. Użyjesz tego formantu jako kontenera nadrzędnego dla innych kontrolek.

    > [!TIP]
    >  Jeśli w dowolnym momencie układ wydają się do poprawnego wyświetlania, Zapisz plik i przełączania się między **projektowania** i **źródła** kart, aby odświeżyć.

4.  W **właściwości** oknie **tła** właściwości (w grupie Style) `#545454`.  Upewnij się, w pozycji w **właściwości** ustawiasz tło okna **RelativeLayout**.

5.  Z **przybornika**, przeciągnij **TextView** kontrolować na **RelativeLayout** kontroli.

6.  W **właściwości** okna ustawiania tych właściwości. (Może to pomóc Aby sortować listę alfabetycznie przy użyciu przycisku Sortuj na pasku narzędzi w oknie właściwości.):

    |Właściwość|Wartość|
    |--------------|-----------|
    |**Tekst**|**Wyszukaj według kod pocztowy**|
    |**id**|`@+id/ZipCodeSearchLabel`|
    |**layout_marginStart**|`10dp`|
    |**textColor**|`@android:color/white`|
    |**textStyle**|`bold`|

    > [!TIP]
    >  Należy zauważyć, że wiele właściwości nie zawierają listy rozwijanej wartości, które można wybrać.  Może być trudne do odgadnięcia, jaka wartość ciągu dla dowolnej podanej właściwości. Masz sugestie, spróbuj wyszukać nazwę właściwości w [ `R.attr` ](http://developer.android.com/reference/android/R.attr.html) klasy strony.
    >
    >  Ponadto wyszukiwania w sieci web szybkiego często prowadzi do strony [ http://stackoverflow.com/ ](http://stackoverflow.com/) inne osoby mają użycia tej samej właściwości.

     Odwołanie, jeśli zaczniesz **źródła** widoku, powinien zostać wyświetlony następujący kod dla tego elementu:

    ```xml
    <TextView
        android:text="Search by Zip Code"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/ZipCodeSearchLabel"
        android:layout_marginStart="10dp"
        android:textColor="@android:color/white"
        android:textStyle="bold" />

    ```

7.  Z **przybornika**, przeciągnij **TextView** kontrolować na **RelativeLayout** kontroli i umieść ją poniżej kontrolki ZipCodeSearchLabel. Upuść nowej kontrolki na odpowiednią krawędzią istniejącej kontrolki. Pomaga ono powiększenia w Projektancie nieco na położenie formantu.

8. W **właściwości** okna ustawiania tych właściwości:

    |Właściwość|Wartość|
    |--------------|-----------|
    |**Tekst**|**Kod pocztowy**|
    |**id**|`@+id/ZipCodeLabel`|
    |**layout_marginStart**|`10dp`|
    |**layout_marginTop**|`6dp`|
    |**textColor**|`@android:color/white`|

    Oto jak kod w **źródła** widok powinien wyglądać:

    ```xml
    <TextView
        android:text="Zip Code"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/ZipCodeSearchLabel"
        android:id="@+id/ZipCodeLabel"
        android:layout_marginStart="10dp"
        android:layout_marginTop="6dp"
        android:textColor="@android:color/white" />
    ```

9. Z **przybornika**, przeciągnij **numer** kontrolować na **RelativeLayout**, umieść ją poniżej **kod pocztowy** etykiety. Następnie ustaw następujące właściwości:

    |Właściwość|Wartość|
    |--------------|-----------|
    |**id**|`@+id/zipCodeEntry`|
    |**layout_marginStart**|`10dp`|
    |**layout_marginBottom**|`10dp`|
    |**width**|`165dp`|
    |**textColor**|`@android:color/white`|

    **Numer** formant jest wpisuje użytkownika w 5 cyfrowy kod pocztowy w Stanach Zjednoczonych. Poniżej przedstawiono kod znaczników, który odnosi się do tej kontrolki:

    ```xml
    <EditText
        android:inputType="number"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/ZipCodeLabel"
        android:id="@+id/zipCodeEntry"
        android:layout_marginStart="10dp"
        android:layout_marginBottom="10dp"
        android:width="165dp"
        android:textColor="@android:color/white" />
    ```

10. Z **przybornika**, przeciągnij **przycisk** na **RelativeLayout** kontroli i umieść ją po prawej stronie formantu zipCodeEntry. Następnie ustaw następujące właściwości:

    |Właściwość|Wartość|
    |--------------|-----------|
    |**id**|`@+id/weatherBtn`|
    |**Tekst**|**Pobierz pogodę**|
    |**layout_marginStart**|`20dp`|
    |**layout_alignBottom**|`@id/zipCodeEntry`|
    |**width**|`165dp`|

    ```xml
    <Button
        android:text="Get Weather"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_toRightOf="@id/zipCodeEntry"
        android:id="@+id/weatherBtn"
        android:layout_marginStart="20dp"
        android:layout_alignBottom="@id/zipCodeEntry"
        android:width="165dp" />
    ```

11. Teraz wiedzieć wystarczająco dużo, aby utworzyć podstawowy interfejs użytkownika przy użyciu narzędzia Android designer. Możesz również tworzyć interfejsu użytkownika, dodając bezpośrednio do znaczników *Main.axml* pliku strony. Tworzenie pozostałą część interfejsu użytkownika, który, przejdź do widoku źródła w projektancie, a następnie wklej następujący kod znaczników *pod* `</RelativeLayout>` tagu końcowego. (Muszą one być poniżej tagu, ponieważ te elementy są *nie* zawarte w `RelativeLayout`.)

    ```xml
    <TextView
        android:text="Location"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/locationLabel"
        android:layout_marginStart="10dp"
        android:layout_marginTop="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/locationText"
        android:layout_marginStart="20dp"
        android:layout_marginBottom="10dp" />
    <TextView
        android:text="Temperature"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/tempLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/tempText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Wind Speed"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/windLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/windText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Humidity"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/humidtyLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/humidityText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Visibility"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/visibilityLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/visibilityText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Time of Sunrise"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/sunriseLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/sunriseText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    <TextView
        android:text="Time of Sunset"
        android:textAppearance="?android:attr/textAppearanceSmall"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/sunsetLabel"
        android:layout_marginStart="10dp" />
    <TextView
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/sunsetText"
        android:layout_marginBottom="10dp"
        android:layout_marginStart="20dp" />
    ```

12. Zapisz plik i przejdź do **projektowania** widoku. Interfejs użytkownika powinien wyglądać w następujący sposób:

     ![Interfejs użytkownika dla aplikacji systemu Android](../cross-platform/media/xamarin_androidui.png)

13. Otwórz **MainActivity.cs**. Oto jak powinien wyglądać kod:

    ```csharp
    protected override void OnCreate (Bundle bundle)
    {
        base.OnCreate (bundle);

        // Set our view from the "main" layout resource
        SetContentView (Resource.Layout.Main);
    }
    ```

14. Skompiluj projekt dla systemu Android, aby sprawdzić swoją pracę. Proces kompilacji dodaje formant identyfikatorów do *Resource.Designer.cs* plików mogą odwoływać się do formantów według nazwy w kodzie.

### <a name="consume-your-shared-code"></a>Korzystanie ze współużytkowanym kodem

1.  Otwórz *MainActivity.cs* pliku **WeatherApp** projektu w edytorze kodu, a następnie zastąp zawartość tego pliku poniższy kod. Ten kod wywołuje `GetWeather` metodę, która jest zdefiniowana w kodzie udostępnionych. Następnie w interfejsie użytkownika aplikacji zawiera dane, które są pobierane z tej metody.

    ```csharp
    using System;
    using Android.App;
    using Android.Widget;
    using Android.OS;

    namespace WeatherApp.Droid
    {
        [Activity(Label = "Sample Weather App",
                  Theme = "@android:style/Theme.Material.Light",
                  MainLauncher = true)]
        public class MainActivity : Activity
        {
            protected override void OnCreate(Bundle bundle)
            {
                base.OnCreate(bundle);

                SetContentView(Resource.Layout.Main);

                Button button = FindViewById<Button>(Resource.Id.weatherBtn);

                button.Click += Button_Click;
            }

            private async void Button_Click(object sender, EventArgs e)
            {
                EditText zipCodeEntry = FindViewById<EditText>(Resource.Id.zipCodeEntry);

                if (!String.IsNullOrEmpty(zipCodeEntry.Text))
                {
                    Weather weather = await Core.GetWeather(zipCodeEntry.Text);
                    FindViewById<TextView>(Resource.Id.locationText).Text = weather.Title;
                    FindViewById<TextView>(Resource.Id.tempText).Text = weather.Temperature;
                    FindViewById<TextView>(Resource.Id.windText).Text = weather.Wind;
                    FindViewById<TextView>(Resource.Id.visibilityText).Text = weather.Visibility;
                    FindViewById<TextView>(Resource.Id.humidityText).Text = weather.Humidity;
                    FindViewById<TextView>(Resource.Id.sunriseText).Text = weather.Sunrise;
                    FindViewById<TextView>(Resource.Id.sunsetText).Text = weather.Sunset;
                }
            }
        }
    }
    ```

    Należy zauważyć, że działanie nadano motyw jasny tła.

### <a name="run-the-app-and-see-how-it-looks"></a>Uruchom aplikację i zobaczyć, jak wygląda

1.  W **Eksploratora rozwiązań**, upewnij się, że **WeatherApp.Droid** projekt jest ustawiony jako projekt startowy.

2.  Wybierz odpowiednie urządzenie lub emulator docelowego, a następnie uruchom aplikację, naciskając klawisz F5.

    > [!NOTE]
    > Jeśli program Visual Studio wskazuje, że projekt systemu Android nie można odnaleźć pliku Newtonsoft.Json, Dodaj pakiet NuGet do projektu dla systemu Android.

3.  Na urządzeniu lub w emulatorze wpisz poprawny kod pocztowy 5 cyfrowy Stanów Zjednoczonych, w polu edycji, a następnie naciśnij klawisz **uzyskać pogody**. Dane o pogodzie dla tego regionu pojawi się w kontrolkach.

    [![Aplikacja Xamarin w systemie Android](../cross-platform/media/cross-plat-xamarin-build-1-android.png)](../cross-platform/media/cross-plat-xamarin-build-1-android-Large.png#lightbox)

> [!TIP]
>  Trwa pełnego kodu źródłowego dla tego projektu [mobile-samples repository w witrynie GitHub](https://github.com/xamarin/mobile-samples/tree/master/Weather).

<a name="Windows" />

## <a name="design-ui-for-windows"></a>Projektowanie interfejsu użytkownika dla Windows

Następnym krokiem jest projektowanie interfejsu użytkownika dla Windows, połącz go ze współużytkowanym kodem, a następnie uruchom aplikację.

### <a name="design-the-look-and-feel-of-your-app"></a>Projektowanie wyglądu i działania aplikacji

 Proces projektowania natywnego interfejsu użytkownika platformy uniwersalnej systemu Windows w aplikacji platformy Xamarin nie różni się od innych natywnej aplikacji platformy uniwersalnej systemu Windows. Z tego powodu użycia projektanta nie omówiono w tym miejscu. Szczegółowe omówienie dotyczą [Tworzenie interfejsu użytkownika przy użyciu projektanta XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).

 Zamiast tego Otwórz *MainPage.xaml* i Zastąp całą zawartość XAML następującym kodem:

```xaml
<Page
    x:Class="WeatherApp.UWP.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:WeatherApp.UWP"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">

        <StackPanel HorizontalAlignment="Left"
                    VerticalAlignment="Top"
                    Height="40" Margin="10,0,0,0" Width="400">
            <TextBlock Text="Weather App" FontSize="30" />
        </StackPanel>
        <StackPanel HorizontalAlignment="Left"
                    VerticalAlignment="Top"
                    Height="120" Margin="10,40,0,0" Width="400"
                    Background="#FF545454">

            <TextBlock Text="Search by Zip Code" TextWrapping="Wrap"
                       HorizontalAlignment="Left" Margin="10,10,0,0"
                       Foreground="White" FontSize="18" FontWeight="Bold" />

            <TextBlock Text="Zip Code" TextWrapping="Wrap"
                       Margin="10,5,0,0" FontSize="14" Foreground="#FFA8A8A8"/>

            <StackPanel Orientation="Horizontal">

                <TextBox x:Name="zipCodeEntry" Text=""
                         Margin="10,10,0,0" VerticalAlignment="Top"
                         InputScope="Number" Width="165" />

                <Button x:Name="weatherBtn" Content="Get Weather"
                        Foreground="White" Width="165" Margin="20,0,0,0" Height="60"
                        Click="GetWeatherButton_Click"/>
            </StackPanel>
        </StackPanel>

        <StackPanel Margin="10,175,0,0">
            <StackPanel.Resources>
                <Style x:Key="commonText" TargetType="TextBlock">
                    <Setter Property="HorizontalAlignment" Value="Left" />
                    <Setter Property="VerticalAlignment" Value="Top" />
                    <Setter Property="TextWrapping" Value="Wrap" />
                </Style>

                <Style x:Key="labelText" TargetType="TextBlock" BasedOn="{StaticResource commonText}">
                    <Setter Property="FontSize" Value="14" />
                    <Setter Property="Foreground" Value="#FFA8A8A8" />
                </Style>

                <Style x:Key="valueText" TargetType="TextBlock" BasedOn="{StaticResource commonText}">
                    <Setter Property="FontSize" Value="18" />
                    <Setter Property="Margin" Value="10, 0, 0, 10" />
                </Style>
            </StackPanel.Resources>

            <TextBlock Text="Location" Style="{StaticResource labelText}" />
            <TextBlock x:Name="locationText" Style="{StaticResource valueText}" />

            <TextBlock Text="Temperature" Style="{StaticResource labelText}" />
            <TextBlock x:Name="tempText" Style="{StaticResource valueText}" />

            <TextBlock Text="Wind Speed" Style="{StaticResource labelText}" />
            <TextBlock x:Name="windText" Style="{StaticResource valueText}" />

            <TextBlock Text="Humidity" Style="{StaticResource labelText}" />
            <TextBlock x:Name="humidityText" Style="{StaticResource valueText}" />

            <TextBlock Text="Temperature" Style="{StaticResource labelText}" />
            <TextBlock x:Name="visibilityText" Style="{StaticResource valueText}" />

            <TextBlock Text="Time of Sunrise" Style="{StaticResource labelText}" />
            <TextBlock x:Name="sunriseText" Style="{StaticResource valueText}" />

            <TextBlock Text="Time of Sunset" Style="{StaticResource labelText}" />
            <TextBlock x:Name="sunsetText" Style="{StaticResource valueText}" />
        </StackPanel>
    </Grid>
</Page>
```

### <a name="consume-your-shared-code"></a>Korzystanie ze współużytkowanym kodem

W *MainPage.xaml.cs* związanym z kodem plik i dodaj następującą obsługę zdarzeń dla przycisku:

```csharp
private async void GetWeatherButton_Click(object sender, RoutedEventArgs e)
{
    if (!String.IsNullOrEmpty(zipCodeEntry.Text))
    {
        Weather weather = await Core.GetWeather(zipCodeEntry.Text);
        locationText.Text = weather.Title;
        tempText.Text = weather.Temperature;
        windText.Text = weather.Wind;
        visibilityText.Text = weather.Visibility;
        humidityText.Text = weather.Humidity;
        sunriseText.Text = weather.Sunrise;
        sunsetText.Text = weather.Sunset;

        weatherBtn.Content = "Search Again";
    }
}
```

Ten kod wywołuje `GetWeather` metodę, która jest zdefiniowana w kodzie udostępnionych. `GetWeather` jest tej samej metody, która wywołana w aplikacji systemu Android. Ten kod zawiera również dane pobrane z tej metody w kontrolek interfejsu użytkownika aplikacji.

### <a name="run-the-app-and-see-how-it-looks"></a>Uruchom aplikację i zobaczyć, jak wygląda

1.  W **Eksploratora rozwiązań**ustaw **WeatherApp.UWP** projekt jako projekt startowy.

2.  W **platformy rozwiązania** listy rozwijanej wybierz pozycję **x86** i wybierz **komputera lokalnego** do wdrożenia aplikacji na pulpicie systemu Windows 10.

3.  Uruchom aplikację, naciskając klawisz **F5** klucza.

4.  Wpisz poprawny kod pocztowy Stanów Zjednoczonych 5 cyfrowy w polu edycji, a następnie naciśnij klawisz **uzyskać pogody**. Dane o pogodzie dla tego regionu pojawi się na stronie.

    [![Aplikacja Xamarin na platformy uniwersalnej systemu Windows](../cross-platform/media/cross-plat-xamarin-build-1-uwp.png)](../cross-platform/media/cross-plat-xamarin-build-1-uwp-Large.png#lightbox)

> [!TIP]
>  Trwa pełnego kodu źródłowego dla tego projektu [mobile-samples repository w witrynie GitHub](https://github.com/xamarin/mobile-samples/tree/master/Weather).

<a name="next" />

## <a name="next-steps"></a>Następne kroki

 **Dodawanie interfejsu użytkownika dla systemu iOS w rozwiązaniu**

 W tym przykładzie należy rozszerzyć przez dodanie natywnego interfejsu użytkownika dla systemu iOS. Aby przetestować kod w systemie iOS, musisz nawiązać połączenie z komputerem Mac w sieci lokalnej, która ma Xcode i Xamarin zainstalowane. Po wykonaniu tej czynności, można użyć narzędzia iOS designer bezpośrednio w programie Visual Studio. Zobacz [mobile-samples repository w witrynie GitHub](https://github.com/xamarin/mobile-samples/tree/master/Weather) dla ukończonej aplikacji.

 Również dotyczyć [Witaj, iOS](/xamarin/ios/get-started/hello-ios/hello-ios-quickstart?tabs=vswin) wskazówki.

 **Dodawanie kodu specyficznego dla platformy w projekcie udostępnionym**

 Udostępniony kod w biblioteki .NET Standard jest niezależny od platformy. Biblioteki po kompilacji i zawarte w każdy pakiet specyficzne dla platformy aplikacji. Jeśli chcesz napisać kod udostępniony, który używa kompilacji warunkowej do izolowania kodu specyficznego dla platformy, możesz użyć *udostępnionego* projektu. Aby uzyskać więcej informacji, zobacz [opcje udostępniania kodu](/xamarin/cross-platform/app-fundamentals/building-cross-platform-applications/practical-code-sharing-strategies).

## <a name="see-also"></a>Zobacz także

- [Dokumentacja platformy Xamarin](http://docs.microsoft.com/xamarin)
- [Centrum deweloperów Windows](https://dev.windows.com/en-us)
- [Plakat krótki SWIFT i C#](http://aka.ms/scposter)
