---
title: 'CA1034: Zagnieżdżone typy nie powinny być widoczne'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
helpviewer_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 14c0837d482341e1ba60191c8b6bb3f5bd8e6dd4
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550950"
---
# <a name="ca1034-nested-types-should-not-be-visible"></a>CA1034: Zagnieżdżone typy nie powinny być widoczne

|||
|-|-|
|TypeName|NestedTypesShouldNotBeVisible|
|CheckId|CA1034|
|Kategoria|Microsoft.Design|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna

Typ widoczny na zewnątrz zawiera deklarację typu widocznego na zewnątrz. Wyliczenia zagnieżdżonych i chronionych typów są wykluczone z tej reguły.

## <a name="rule-description"></a>Opis reguły
 Typ zagnieżdżony to typ zadeklarowany wewnątrz zakresu innego typu. Zagnieżdżone typy są przydatne do enkapsulacji szczegółów implementacji prywatnej typu zawierającego. Używane w tym celu typy zagnieżdżone nie powinny być widoczne na zewnątrz.

 Nie używaj widocznego na zewnątrz typy zagnieżdżone powodują ustawienie logicznego grupowania lub aby uniknąć konfliktów nazw; Zamiast tego należy użyć przestrzeni nazw.

 Zagnieżdżone typy obejmują pojęcie dostępność składowej, która niektórych programistów niezrozumiały wyraźnie.

 Typy chronionych może służyć w podklasy i zagnieżdżone typy w scenariuszach Dostosowywanie zaawansowane.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Jeśli nie ma typu zagnieżdżonego, aby być widoczne na zewnątrz, zmień dostępność typu. W przeciwnym razie Usuń typu zagnieżdżonego od jego elementu nadrzędnego. Jeśli zagnieżdżania ma na celu kategoryzowania typu zagnieżdżonego, należy użyć przestrzeni nazw w zamian tworzenie hierarchii.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 Poniższy przykład pokazuje typ, który narusza regułę.

 [!code-cpp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CPP/ca1034-nested-types-should-not-be-visible_1.cpp)]
 [!code-csharp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CSharp/ca1034-nested-types-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/VisualBasic/ca1034-nested-types-should-not-be-visible_1.vb)]