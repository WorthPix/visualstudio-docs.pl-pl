---
title: 'CA2240: Należy poprawnie zaimplementować ISerializable'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2240
- ImplementISerializableCorrectly
helpviewer_keywords:
- CA2240
- ImplementISerializableCorrectly
ms.assetid: cf05936d-0d6c-49ed-a1b4-220032e50b97
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2cf56f8fc692b79ef6e0c1b19bcbd3de4a1f647f
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45548387"
---
# <a name="ca2240-implement-iserializable-correctly"></a>CA2240: Należy poprawnie zaimplementować ISerializable

|||
|-|-|
|TypeName|ImplementISerializableCorrectly|
|CheckId|CA2240|
|Kategoria|Microsoft.Usage|
|Zmiana kluczowa|Bez podziału|

## <a name="cause"></a>Przyczyna

Typ widoczny na zewnątrz jest można przypisać do <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> interfejsu i jeden z następujących warunków jest spełniony:

- Typ dziedziczy, ale nie przesłania <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> metoda i typ deklaruje pola wystąpienia, które nie są oznaczone przez <xref:System.NonSerializedAttribute?displayProperty=fullName> atrybutu.

- Typ nie jest zapieczętowany i typ implementuje <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metodę, która jest zewnętrznie niewidoczny i którą można przesłonić.

## <a name="rule-description"></a>Opis reguły
 Wystąpienia pól, które są zadeklarowane w typie, który dziedziczy <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> interfejsu nie są automatycznie uwzględnione w procesie serializacji. Aby dołączyć pola, typ musi zawierać implementację <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metod i konstruktorów serializacji. Jeśli pola nie powinien podlegać serializacji, zastosuj <xref:System.NonSerializedAttribute> atrybutu do pola, aby jawnie wskazać decyzji.

 Typy, które nie są zamknięte, implementacje <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda powinna być widoczna na zewnątrz. W związku z tym metoda może być wywoływany przez typy pochodne i jest możliwym do zastąpienia.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> metoda widoczna oraz możliwa do zastąpienia i upewnij się, że wszystkie pola wystąpienia są uwzględnione w procesie serializacji lub jawnie oznaczone <xref:System.NonSerializedAttribute> atrybutu.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 Poniższy przykład przedstawia dwa typy możliwych do serializacji, które naruszają zasady.

 [!code-csharp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_1.cs)]
 [!code-cpp[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_1.cpp)]
 [!code-vb[FxCop.Usage.ImplementISerializableCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_1.vb)]

## <a name="example"></a>Przykład
 Poniższy przykład naprawia dwóch poprzednich naruszenia, zapewniając zastąpienie implementację <xref:System.Runtime.Serialization.ISerializable.GetObjectData> klasy książki i udostępnienie implementację `GetObjectData` klasy biblioteki.

 [!code-cpp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CPP/ca2240-implement-iserializable-correctly_2.cpp)]
 [!code-csharp[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/CSharp/ca2240-implement-iserializable-correctly_2.cs)]
 [!code-vb[FxCop.Usage.ImplementISerializableCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca2240-implement-iserializable-correctly_2.vb)]

## <a name="related-rules"></a>Powiązane reguły

- [CA2236: Wywołuj metody klasy podstawowej w typach ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)
- [CA2229: Zaimplementuj konstruktory serializacji](../code-quality/ca2229-implement-serialization-constructors.md)
- [CA2238: Zaimplementuj poprawnie metody serializacji](../code-quality/ca2238-implement-serialization-methods-correctly.md)
- [CA2235: Oznacz wszystkie pola nieprzeznaczone do serializacji](../code-quality/ca2235-mark-all-non-serializable-fields.md)
- [CA2237: Oznacz typy ISerializable za pomocą atrybutu SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)
- [CA2239: Określ metody deserializacji dla pól opcjonalnych](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)
- [CA2120: Zabezpiecz konstruktory serializacji](../code-quality/ca2120-secure-serialization-constructors.md)