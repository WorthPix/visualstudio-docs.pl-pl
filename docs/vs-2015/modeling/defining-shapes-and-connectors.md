---
title: Definiowanie kształtów i łączników | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fae548d-9288-4dd5-a24f-ff0d69c73628
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 4ee3bfaac9cfcdf887a22c84e0b98a13f8add7ab
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49244611"
---
# <a name="defining-shapes-and-connectors"></a>Definiowanie kształtów i łączników
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Istnieje kilka typów podstawowych kształtów, które mogą być używane do wyświetlania informacji na diagramie w języku specyficznym dla domeny (DSL).  
  
##  <a name="shapeTypes"></a> Podstawowe typy kształtów i łączników  
 DSL diagram zawiera zbiór *kształty* powiązane liniami lub *łączników*.  Zwykle, ale nie zawsze:  
  
-   Kształty są widoczne reprezentacja elementów modelu.  
  
-   Łączniki reprezentują relacje odniesienia.  
  
-   Diagram przedstawia wystąpienie katalogu głównego modelu.  
  
-   Osadzanie relacje między elementami modelu są wyświetlane przez relację zawierania. Na przykład elementów reprezentujących porty składnika są osadzone w składniku.  
  
 Te wzorce nie są wymuszane, ale mocno są obsługiwane. Podczas projektowania DSL ponosi należy pamiętać, że projekt relacji osadzania powinien być wpływ, jaki chcesz przedstawić modelu na ekranie. Z drugiej strony relacje odniesienia powinien odzwierciedlać pojęcia domeny biznesowej.  
  
 Dostępne są następujące typy kształtów:  
  
|Typ kształtu|Opis|  
|----------------|-----------------|  
|Kształt geometryczny|Kształt prostokątne lub eliptycznego ogólnego przeznaczenia. Możesz wyświetlić tekst i ikona dekoratory w określonym położeniu względem granic kształtu.<br /><br /> Aby zagnieździć kształty wewnątrz kształtów geometrycznych, zobacz [zagnieżdżanie kształtów](../modeling/nesting-shapes.md).|  
|Kształt przedziału|Prostokąt zawierający nagłówek i przedziały, takich jak klasy UML. Każdego przedziału może zawierać listę wierszy tekstu.<br /><br /> Wiersze reprezentują zazwyczaj elementy osadzone w elemencie reprezentowany przez kształt. Na przykład utworzyć DSL za pomocą szablonu rozwiązania diagramów klas.|  
|Kształt obrazu|Kształt wyświetlający obraz.|  
|Kształt portu|Niewielki prostokąt przeznaczone do dołączenia do konturu innego kształtu. Zazwyczaj używane w modelach składnika.<br /><br /> Element modelu reprezentowanego przez port jest zwykle osadzona w element reprezentowany przez kształtu nadrzędnego. Na przykład utworzyć DSL za pomocą szablonu rozwiązania składniki.<br /><br /> Domyślnie kształt portu można przesunąć wzdłuż boków jego obiektu nadrzędnego. Można zdefiniować zasadę granice, aby ograniczyć go do określonej pozycji.<br /><br /> Tworząc kształt portu bardzo małe i przejrzystości, umożliwia on stanowią punkt połączenia stałej powierzchni z boku jego kształtu nadrzędnego.|  
|Torów|Tory podzielić diagramu na poziomą lub pionową segmentów. Tor zawsze pozostaje poniżej innych kształtów na diagramie.<br /><br /> Zazwyczaj elementy modelu toru są elementem nadrzędnym w katalogu głównym modelu i inne elementy są elementem nadrzędnym na nich. Na przykład utworzyć DSL za pomocą szablonu rozwiązania przepływu zadań.|  
|Łączniki|Linii między kształtami zazwyczaj reprezentują relacje odniesienia. Można ustawić opcje, aby bezpośrednio lub prostoliniowego łącznika i mają różne typy grot strzałki.|  
  
##  <a name="shapeInheritance"></a> Kształt dziedziczenia  
 Kształt może dziedziczyć z innego kształtu. Jednak kształty muszą być tego samego rodzaju. Na przykład kształt geometryczny może dziedziczyć kształt geometryczny. Kształty dziedziczone mają przedziały i dekoratory ich kształtu podstawowego. Łączniki mogą dziedziczyć łączników.



