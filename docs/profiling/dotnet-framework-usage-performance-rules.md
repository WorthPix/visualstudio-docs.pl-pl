---
title: Zasady wydajności użycia frameworku .NET | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ab573755-6370-48aa-853d-a7321c424c79
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1903b61fce39bdd68b471472530857d720bac906
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766025"
---
# <a name="net-framework-usage-performance-rules"></a>Reguły wydajności dotyczące użycia programu .NET Framework
Reguły wydajności środowiska.NET Framework użycia kategorii zidentyfikować konkretnych metod, które mogą być optymalizowane, a także identyfikowania wzorców użycia bardziej ogólne, takie jak odzyskiwanie pamięci i rywalizacji blokad, które mogą zostać sprawdzone pod kątem problemów z wydajnością.  
  
|||  
|-|-|  
|[DA0001: Użyj klasy StringBuilder do konkatenacji](../profiling/da0001-use-stringbuilder-for-concatenations.md)|Wywołuje się <xref:System.String.Concat(System.String,System.String)?displayProperty=fullName> są znaczna część danych profilowania. Należy rozważyć użycie <xref:System.Text.StringBuilder> klasy w celu tworzenia ciągów z wieloma segmentami.|  
|[DA0005: Częste odzyskiwanie pamięci GC2](../profiling/da0005-frequent-gc2-collections.md)|Stosunkowo dużej liczby obiektów pamięci .NET jest odzyskane w generacji 2 wyrzucanie elementów bezużytecznych. Jeśli zbyt wiele obiektów o krótkim okresie przetrwać kolekcji generacji 1, kosztów zarządzania pamięci może łatwo stać się nadmierne.|  
|[DA0006: Przesłoń metody Equals() dla typów wartości](../profiling/da0006-override-equals-parens-for-value-types.md)|Wywołuje się `Equals` metody lub operatory równości typu publicznego wartości są znaczna część danych profilowania. Rozważ zaimplementowanie bardziej efektywną metodą.|  
|[DA0007: Unikanie używania wyjątków do przepływu sterowania](../profiling/da0007-avoid-using-exceptions-for-control-flow.md)|Wysoki współczynnik programów obsługi wyjątków .NET Framework zostały wywołane w danych profilowania. Należy rozważyć użycie innych logika przepływu sterowania, aby zmniejszyć liczbę wyjątków, które są generowane.|  
|[DA0010: Kosztowna funkcja GetHashCode](../profiling/da0010-expensive-gethashcode.md)|Wywołuje się `GetHashCode` metody typu są znaczna część danych profilowania lub `GetHashCode` metody przydziela pamięć. Upraszczanie metody.|  
|[DA0011: Kosztowna funkcja CompareTo](../profiling/da0011-expensive-compareto.md)|`CompareTo` Metody typu jest kosztowna lub metoda przydziela pamięć. Należy zmniejszyć złożoność `CompareTo` metody.|  
|[DA0012: Znaczne odbicie](../profiling/da0012-significant-amount-of-reflection.md)|Wywołuje się <xref:System.Reflection?displayProperty=fullName> metod, takich jak <xref:System.Reflection.IReflect.InvokeMember%2A> i <xref:System.Reflection.IReflect.GetMember%2A> lub metod typu <xref:System.Type.InvokeMember%2A> są znaczna część danych profilowania. Jeśli to możliwe, należy wziąć pod uwagę zastępuje tych metod z wczesnym powiązaniem, które metody zestawów zależnych.|  
|[DA0013: Znaczące wykorzystanie funkcji String.Split i String.Substring](../profiling/da0013-high-usage-of-string-split-or-string-substring.md)|Wywołuje się <xref:System.String.Split%2A?displayProperty=fullName> lub <xref:System.String.Substring%2A> metody są znaczna część danych profilowania. Należy rozważyć użycie <xref:System.String.IndexOf%2A> lub <xref:System.String.IndexOfAny%2A> podczas testowania istnienie substring w ciągu.|  
|[DA0018: Aplikacja 32-bitowa działa w granicach pamięci zarządzanej dla procesu](../profiling/da0018-32-bit-application-running-at-process-managed-memory-limits.md)|Dane systemowe, które są zbierane podczas przebiegu profilowania wskazuje, że pamięci .NET Framework sterty osiągnięciu maksymalnego rozmiaru zarządzanych stosów może nawiązać połączenie w procesie 32-bitowych. Należy rozważyć profilowanie ponownie przy użyciu metody profilowania pamięci .NET i optymalizacji wykorzystania zasobów zarządzanych przez aplikację.|  
|[DA0021: Duża częstotliwość odzyskiwania pamięci generacji 1](../profiling/da0021-high-rate-of-gen-1-garbage-collections.md)|Stosunkowo dużej liczby obiektów pamięci .NET jest odzyskane w generacji 1 wyrzucanie elementów bezużytecznych. Jeśli zbyt wiele obiektów o krótkim okresie przetrwać kolekcji pokolenia 0, kosztów zarządzania pamięcią można łatwo stają się nadmierne.|  
|[DA0022: Duża częstotliwość odzyskiwania pamięci generacji 2](../profiling/da0022-high-rate-of-gen-2-garbage-collections.md)|Duża liczba obiektów pamięci .NET jest odzyskane w generacji 2 wyrzucanie elementów bezużytecznych. Jeśli zbyt wiele obiektów o krótkim okresie przetrwać kolekcji generacji 1, kosztów zarządzania pamięci może łatwo stać się nadmierne. Ta zasada generowane, gdy liczba rywalizacji blokad przekracza próg górny wartość reguły DA0005.|  
|[DA0023: Duże zużycie czasu procesora CPU przez odzyskiwanie pamięci](../profiling/da0023-high-gc-cpu-time.md)|Dane wydajności systemu, które są zbierane podczas profilowania oznacza ilość czasu przeznaczonego na wyrzucanie elementów bezużytecznych — w znaczący w porównaniu z czasem przetwarzania całkowita liczba aplikacji.|  
|[DA0024: Nadmierne GC CPU czasu](../profiling/da0024-excessive-gc-cpu-time.md)|Dane wydajności systemu, które są zbierane podczas profilowania wskazuje, że ilość czasu przeznaczonego na wyrzucanie elementów bezużytecznych — w jest zbyt wysoka w porównaniu z czasem przetwarzania całkowita liczba aplikacji. Ta zasada generowane, gdy czas spędzony w pamięci przekracza wartość górnej wartości progowej reguły DA0023.|  
|[DA0038: Wysoka liczba rywalizacji blokad](../profiling/da0038-high-rate-of-lock-contentions.md)|Dane wydajności systemu, które są zbierane z danych profilowania wskazuje znacznie wysoka liczba rywalizacji blokad, który wystąpił podczas wykonywania aplikacji. Należy rozważyć profilowanie, aby znaleźć przyczynę rywalizacji ponownie, używając metoda profilowania współbieżności.|  
|[DA0039: Bardzo wysoka liczba rywalizacji blokad](../profiling/da0039-very-high-rate-of-lock-contentions.md)|Dane wydajności systemu, które są zbierane z danych profilowania wskazuje zbyt wysoka liczba rywalizacji blokad, który wystąpił podczas wykonywania aplikacji. Należy rozważyć profilowanie, aby znaleźć przyczynę rywalizacji ponownie, używając metoda profilowania współbieżności. Ta zasada generowane, gdy liczba rywalizacji blokad przekracza próg górny wartość reguły DA0038.|