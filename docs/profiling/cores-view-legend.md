---
title: Widok rdzeni — Legenda | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.cores.legend
helpviewer_keywords:
- Concurrency Visualizer, Cores View Legend
ms.assetid: e160384c-fcfe-49b3-86b7-229adb736c51
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ee31b1547f9607f54cc5db9d056b997f071633ff
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34691590"
---
# <a name="cores-view-legend"></a>Widok rdzeni — Legenda
Widok rdzeni — Legenda identyfikuje każdy wątek, kolor i nazwę. Zawiera kolumny, które zawierają liczby przełączeń kontekstu różnych rdzeniach, przełączeń kontekstu całkowitej i procent przełączeń kontekstu przecinających rdzenie. Wiersze w legendzie są sortowane według liczby przełączeń kontekstu różnych rdzeniach, w kolejności malejącej.  
  
 Możesz wybrać wiersze legendy do filtrowania wątków, które są wyświetlane na osi czasu. Tylko wybrane wątki są wyświetlane na osi czasu. Jeśli nie wybrano żadnych wierszy, wszystkie wiersze są wyświetlane na osi czasu.  
  
 Kontekst różnych rdzeniach zmienia koszt koszty i wydajność w ponad przełączników, które pozostają na tego samego rdzenia logicznego. Podczas przełączeń kontekstu rejestrów procesora jest zapisywany i przywracany, wykonywany jest kod jądra systemu operacyjnego translacji równoległej buforu wpisy są ładowane i procesora potok jest opróżniany. Przełączenia kontekstu różnych rdzeniach może być nawet droższe niż inne przełączenia kontekstu, ponieważ dane pamięci podręcznej jest nieprawidłowa dla tego wątku w innym core. Z kolei jeśli kontekst przełączona na podstawowy, który wcześniej został uruchomiony wątek, istnieje prawdopodobieństwo, że przydatne dane są nadal w pamięci podręcznej. Zwiększono przełączeń kontekstu core między próbami Zarządzanie wątku spada koligacji i wydajności, rozważyć, czy w celu rozwiązania tego problemu. Uruchom przez wyeliminowanie koligacji wątków, a następnie sprawdź efekty różnych rdzeniach.  
  
 W poniższej tabeli opisano elementy legendy.  
  
|Element|Definicja|  
|-------------|----------------|  
|Nazwa wątku|Zawiera kolor wątku w poprzednim oś czasu rdzeni i nazwę tego wątku.|  
|Przełączenia kontekstu różnych rdzeniach|Liczba przełączeń kontekstu dla wątku, który również przełączono z jednego rdzenia logicznego do innego. Go nie odróżnić przełączenia kontekstu różnych rdzeniach, które przechodzą z jednym procesorem struktury do drugiej i tych, które pozostają w tej samej struktury.|  
|Przełączenia kontekstu całkowita|Całkowita liczba przełączeń kontekstu dla danego wątku w okresie próbkowania. Zalicza się każdej zmianie wątku jedno przełączenie kontekstu kontekstu (na przykład pochodzący z wykonania na synchronizacji).|  
|Procent przełączeń kontekstu przecinających rdzenie|Obliczony jako procent przez podzielenie liczby przełączeń kontekstu różnych rdzeniach według liczby przełączeń kontekstu całkowitej. Im większa tej wartości procentowej, tym większy efekt narzut na różnych rdzeniach kontekstu zmienia się na wydajność tego konkretnego wątku.|  
  
## <a name="see-also"></a>Zobacz także  
 [Widok rdzeni](../profiling/cores-view.md)