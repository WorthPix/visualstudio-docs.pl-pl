---
title: 'CA2004: Usuń wywołania do GC.KeepAlive'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
helpviewer_keywords:
- RemoveCallsToGCKeepAlive
- CA2004
ms.assetid: bc543b5b-23eb-4b45-abc2-9325cd254ac2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3845826ef1c88eaa40c8cf05936080eb320bdecc
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45546814"
---
# <a name="ca2004-remove-calls-to-gckeepalive"></a>CA2004: Usuń wywołania do GC.KeepAlive
|||
|-|-|
|TypeName|RemoveCallsToGCKeepAlive|
|CheckId|CA2004|
|Kategoria|Microsoft.Reliability|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna
 Użyj klasy `SafeHandle` , ale nadal zawiera wywołania `GC.KeepAlive`.

## <a name="rule-description"></a>Opis reguły
 Jeśli są konwertowane na `SafeHandle` użycia, usunąć wszystkie wywołania `GC.KeepAlive` (obiekt). W tym przypadku klasy nie powinny wywołać `GC.KeepAlive`, zakładając, że nie ma finalizatora, ale korzystają z `SafeHandle` do ukończenia dojście systemu operacyjnego dla nich.  Chociaż koszt pozostawienie w wywołaniu `GC.KeepAlive` może być niewielkie, mierzony wydajność, wrażenie, wywołanie `GC.KeepAlive` jest konieczne lub wystarczające, aby rozwiązać problem, który może już nie istnieć sprawia, że kod jest trudniejsze okres istnienia Obsługa.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Usuń wywołania `GC.KeepAlive`.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Można pominąć to ostrzeżenie, tylko wtedy, gdy nie jest technicznie poprawny do przekonwertowania na `SafeHandle` użycia w klasie.