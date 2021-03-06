---
title: 'DA0014: Wyjątkowo wysoki stopień stronicowania aktywnej pamięci na dysk | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAMemoryBound
- vs.performance.DA0014
- vs.performance.14
- vs.performance.rules.DA0014
ms.assetid: a7fa3749-9191-437a-9331-9d917181e62f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d0d73bff2090e74dfdfdf3d360af961b379b33e8
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34750158"
---
# <a name="da0014-extremely-high-rates-of-paging-active-memory-to-disk"></a>DA0014: Wyjątkowo wysoki stopień stronicowania aktywnej pamięci na dysku
|||  
|-|-|  
|Identyfikator reguły|DA0014|  
|Kategoria|Pamięci i stronicowania|  
|Metoda profilowania|Wszystkie|  
|Komunikat|Występuje skrajnie intensywne stronicowanie aktywnej pamięci na dysk. Ta aplikacja może być zależna od pamięci.|  
|Typ reguły|Ostrzeżenie|  
  
 Gdy profilu można za pomocą próbkowania, pamięci platformy .NET lub metody kontencji zasobów, należy zebrać co najmniej 25 próbek do wyzwolenia tej reguły.  
  
## <a name="cause"></a>Przyczyna  
 Dane o wydajności systemu, który został zebrany w przebiegu profilowania wskazuje skrajnie intensywne stronicowanie aktywnej pamięci do i z dysku, które wystąpiły w przebiegu profilowania. Stronicowanie stawki na tym poziomie zwykle wpływa na wydajność aplikacji i elastyczność. Rozważ zmniejszenie przez modyfikowanie algorytmów alokacji pamięci. Masz może również wziąć pod uwagę wymagania dotyczące pamięci aplikacji. uruchomione profilowanie ponownie na komputerze więcej pamięci.  
  
## <a name="rule-description"></a>Opis reguły  
 Nadmiernego stronicowania na dysku może być spowodowane brakiem pamięci fizycznej. Jeśli operacja stronicowania dominują w aplikacjach użycie dysku fizycznego, w którym znajduje się plik stronicowania, mogą one spowolnić inne operacje dysku ukierunkowane na zastosowanie do tego samego dysku.  
  
 Często, strony są dysku zapisu lub odczytu z dysku podczas operacji stronicowania zbiorczego. Liczba stron wyjścia na sekundę jest często znacznie większa niż liczba zapisy stron/s, na przykład. Ponieważ dane wyjściowe strony na sekundę obejmuje również strony zmienione dane z pamięci podręcznej systemu plików. Jednak nie zawsze jest łatwo określić, które procesy są bezpośrednio odpowiedzialne za stronicowania lub dlaczego.  
  
> [!NOTE]
>  Ta zasada generowane, gdy stopień stronicowania aktywnej pamięci osiągną bardzo wysoki współczynnik. Informacyjny reguły, jeśli poziom stronicowania jest istotne, ale nie extreme [DA0017: wysoki stopień stronicowania aktywnej pamięci na dysk](../profiling/da0017-high-rates-of-paging-active-memory-to-disk.md) generowane w zamian.  
  
## <a name="how-to-fix-violations"></a>Jak rozwiązać naruszeń  
 Kliknij dwukrotnie komunikat w oknie Lista błędów, aby przejść do [znaczniki](../profiling/marks-view.md) widoku. Znajdź **Pamięć\Strony/s** kolumny. Określa, czy określone fazy wykonywania programu stronicowania działania We/Wy w przypadku większych niż inne.  
  
 Jeśli zbiera dane profilu dla aplikacji ASP.NET w scenariuszu testowania obciążenia, spróbuj uruchomić ponownie test obciążenia na komputerze, skonfigurować przy użyciu dodatkowej pamięci fizycznej (lub pamięci RAM).  
  
 Rozważ zmniejszenie przydziału pamięci zmiana algorytmów i unikanie pamięć interfejsów API, takich jak String.concat — i String.Substring.