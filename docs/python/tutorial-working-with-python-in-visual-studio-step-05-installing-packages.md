---
title: Praca z pakietami instalacji języka Python — samouczek, krok 5
description: Krok 5 przewodnika podstawowe możliwości języka Python w programie Visual Studio, demonstrując funkcje zarządzania pakietami w środowisku Python za pomocą programu Visual Studio.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: fdc37c35d2563780804c38fb6a74e1574cfaa6ad
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546680"
---
# <a name="step-5-install-packages-in-your-python-environment"></a>Krok 5: Instalowanie pakietów w środowisku Python

**Poprzedni krok: [uruchamianie kodu w debugerze](tutorial-working-with-python-in-visual-studio-step-04-debugging.md)**

Fora społeczności deweloperów języka Python tworzył tysiące przydatne pakiety, które można zastosować do własnych projektów. Program Visual Studio udostępnia interfejs użytkownika w zakresie zarządzania pakietami w środowisku Python.

1. Wybierz **widoku** > **Windows inne** > **środowiska Python** polecenia menu. **Środowiska Python** zostanie otwarte okno jako element równorzędny do **Eksploratora rozwiązań** i pokazuje różnych środowisk dostępnych dla Ciebie. Lista obejmuje zarówno środowisk, w których został zainstalowany przy użyciu Instalatora programu Visual Studio i te, które należy zainstalować osobno. Środowisko wytłuszczonym drukiem jest środowiska domyślnego, który jest używany dla nowych projektów.

  ![Okno środowiska Python](media/environments-default-view-blue.png)

1. Środowisko **Przegląd** kartę zapewnia szybki dostęp do **Interactive** okna dla danego środowiska, wraz z folderu instalacji i interpreterów środowiska. Na przykład wybierz **Otwórz okno interaktywne** i **Interactive** w programie Visual Studio pojawia się okno na tym konkretnym środowisku.

1. Wybierz **pakietów** kartę i wyświetlić listę pakietów, które są aktualnie zainstalowane w środowisku.

  ![Zainstalowane pakiety w środowisku](media/environments-installed-packages-blue.png)

1. Zainstaluj `matplotlib` , wprowadzając jego nazwę w polu wyszukiwania, następnie wybierz pozycję **instalowanie narzędzia pip**

  ![Instalowanie matplotlib w środowisku](media/environments-add-matplotlib1.png)

1. Zgoda na podniesienie uprawnień, jeśli zostanie wyświetlony monit, aby to zrobić.

1. Po zainstalowaniu pakietu pojawia się w **środowiska Python** okna. **X** po prawej stronie pakietu odinstalowuje go.

  ![Ukończenie instalacji matplotlib w środowisku](media/environments-add-matplotlib2.png)

  Pasek postępu małych może pojawić się poniżej środowiska, aby wskazać, że Visual Studio tworzy jego bazy danych IntelliSense dla nowo zainstalowanego pakietu. **IntelliSense** karcie znajdują się też więcej szczegółowych informacji. Należy pamiętać, że do czasu ukończenia tej bazy danych IntelliSense funkcje, takie jak automatyczne uzupełnianie i sprawdzanie składni nie będzie aktywny w edytor dla tego pakietu.

  Należy pamiętać, że **programu Visual Studio 2017 w wersji 15.6** później używa różnych i szybsze metody do pracy z obsługą technologii IntelliSense i wyświetla komunikat w tym celu na **IntelliSense** kartę.

1. Utwórz nowy projekt za pomocą **pliku** > **New** > **projektu**, wybierając opcję **aplikację w języku Python** szablon. W pliku kodu, który pojawia się Wklej następujący kod, który tworzy tylko tym razem, które są oznaczane na wykresach graficznie wave cosinus, takich jak poprzednie kroki samouczka:

    ```python
    from math import radians
    import numpy as np     # installed with matplotlib
    import matplotlib.pyplot as plt

    def main():
        x = np.arange(0, radians(1800), radians(12))
        plt.plot(x, np.cos(x), 'b')
        plt.show()

    main()
    ```

1. Uruchom program z (**F5**) lub bez debugera (**Ctrl**+**F5**) aby wyświetlić dane wyjściowe:

  ![Dane wyjściowe z przykładu matplotlib](media/environments-add-matplotlib3.png)

## <a name="next-step"></a>Następny krok

> [!div class="nextstepaction"]
> [Praca z usługą Git](tutorial-working-with-python-in-visual-studio-step-06-working-with-git.md)

## <a name="go-deeper"></a>Przejdź dalej

- [Środowiska Python](managing-python-environments-in-visual-studio.md)
