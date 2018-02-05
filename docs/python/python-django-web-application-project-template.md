---
title: "Szablon projektu sieci web Django dla języka Python w programie Visual Studio | Dokumentacja firmy Microsoft"
description: "Przegląd szablonów programu Visual Studio dla aplikacji sieci web napisanych w języku Python za pomocą środowiska Django."
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: def92979f4ea8902a204728ebb08863f0eb8fb6a
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2018
---
# <a name="django-web-project-template"></a>Szablon projektu sieci web Django

[Django](https://www.djangoproject.com/) to struktura Python wysokiego poziomu przeznaczone do rozwoju szybkie, bezpieczne i skalowalne sieci web. Obsługa języka Python w programie Visual Studio zapewnia szablon projektu, aby skonfigurować strukturę aplikacji sieci web opartych na Django. Aby użyć szablonu w programie Visual Studio, wybierz opcję **Plik > Nowy > Projekt**, wyszukaj "Django" i wybierz **projektu sieci Web Django** szablonu. Projekt wynikowy zawiera schematyczny kod, a także domyślnej bazy danych SQLite. **Pusty projekt sieci Web Django** szablon jest podobny, ale nie ma bazy danych.

Program Visual Studio udostępnia pełną IntelliSense dla projektów Django:

- Zmienne kontekstu przekazywany do szablonu:

    ![IntelliSense dla kontekstu zmiennych](media/template-django-intellisense.png)

- Znakowanie i filtrowania dla obu built-ins i zdefiniowanych przez użytkownika:

    ![IntelliSense dla tagów i filtry](media/template-django-intellisense-filter.png)

- Składnia kolorowaniu osadzonych CSS i JavaScript:

    ![CSS, IntelliSense](media/template-django-intellisense-css.png)

    ![JavaScript IntelliSense](media/template-django-intellisense-js.png)

Visual Studio udostępnia pełnej [obsługa debugowania](debugging-python-in-visual-studio.md) dla projektów Django: 

![Punkty przerwania](media/template-django-debugging.png)

Jest typowa dla projektów Django mają być zarządzane za pośrednictwem ich `manage.py` pliku, który jest założenie, że program Visual Studio jest zgodny. Zatrzymanie przy użyciu tego pliku jako punkt wejścia, Podziel są zasadniczo pliku projektu. W takim przypadku należy [ponownie utworzyć projekt z istniejących plików](managing-python-projects-in-visual-studio.md#creating-a-project-from-existing-files) bez oznaczenie go jako projekt Django.

## <a name="django-management-console"></a>Konsoli zarządzania Django

W konsoli zarządzania Django jest dostępny za pośrednictwem różnych poleceń na **projektu** menu lub klikając prawym przyciskiem myszy projekt w Eksploratorze rozwiązań.

- **Otwórz powłokę Django...** : otwiera powłokę w kontekście użytkownika aplikacji, który umożliwia manipulowanie modeli "

    ![Konsola](media/template-django-console-shell.png)

- **Baza danych synchronizacji Django**: wykonuje `manage.py syncdb` w oknie interaktywnym:

    ![Konsola](media/template-django-console-sync-db.png)

- **Zbieraj Static**: wykonuje `manage.py collectstatic --noinput` można skopiować pliki statyczne do ścieżka określona przez `STATIC_ROOT` w Twojej `settings.py`. Należy pamiętać, że w przypadku [publikowanie do systemu Microsoft Azure](python-web-application-project-templates.md#publishing-to-azure-app-service), pliki statyczne są zbierane automatycznie w ramach operacji publikowania.

    ![Konsola](media/template-django-console-collect-static.png)

- **Sprawdź poprawność**: wykonuje `manage.py validate`, które raporty wszelkie błędy sprawdzania poprawności zainstalowane modele określony przez `INSTALLED_APPS` w Twojej `settings.py`:

    ![Konsola](media/template-django-console-validate.png)