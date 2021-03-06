---
title: 'CA2227: Właściwości kolekcji powinny być tylko do odczytu'
ms.date: 09/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: f1bbd3e6ba97d969694e7d2142978c12552b3c50
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2018
ms.locfileid: "47860254"
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227: Właściwości kolekcji powinny być tylko do odczytu

|||
|-|-|
|TypeName|CollectionPropertiesShouldBeReadOnly|
|CheckId|CA2227|
|Kategoria|Microsoft.Usage|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna

Właściwość widocznego na zewnątrz, zapisywalny, jest typ, który implementuje <xref:System.Collections.ICollection?displayProperty=fullName>. Ta zasada powoduje ignorowanie tablic, indeksatory (właściwości o nazwie "Item") i zestawów uprawnień.

## <a name="rule-description"></a>Opis reguły

Właściwość zapisywalnej kolekcji pozwala użytkownikowi zastąpić kolekcję całkowicie inną kolekcję. Właściwość tylko do odczytu zatrzymanie zastępowanie kolekcji, ale nadal umożliwia poszczególnych elementów członkowskich do ustawienia. Zastępowanie kolekcji celem jest wzorzec projektowy preferowanych czy metodę, aby usunąć wszystkie elementy z kolekcji i metodę, aby wypełnić kolekcję. Zobacz <xref:System.Collections.ArrayList.Clear%2A> i <xref:System.Collections.ArrayList.AddRange%2A> metody <xref:System.Collections.ArrayList?displayProperty=fullName> klasy, na przykład tego wzorca.

Plik binarny i serializacji XML obsługuje właściwości tylko do odczytu, które są kolekcjami. <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> Klasa ma określonych wymagań dotyczących typów, które implementują <xref:System.Collections.ICollection> i <xref:System.Collections.IEnumerable?displayProperty=fullName> aby podlegać serializacji.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia

Aby naprawić naruszenie tej zasady, należy ustawić właściwość jako tylko do odczytu. Jeśli projekt wymaga, należy dodać metody, aby usunąć i ponownie wypełnić kolekcję.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia

Można pominąć to ostrzeżenie, jeśli właściwość jest częścią [obiekt transferu danych (DTO)](/previous-versions/msp-n-p/ff649585(v=pandp.10)) klasy.

W przeciwnym razie nie Pomijaj ostrzeżeń od tej reguły.

## <a name="example"></a>Przykład

W poniższym przykładzie przedstawiono typ z właściwość zapisywalnej kolekcji i pokazuje, jak kolekcji można zastąpić bezpośrednio. Ponadto pokazuje preferowany sposób zastąpienia właściwość kolekcji tylko do odczytu za pomocą `Clear` i `AddRange` metody.

[!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CSharp/ca2227-collection-properties-should-be-read-only_1.cs)]
[!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/VisualBasic/ca2227-collection-properties-should-be-read-only_1.vb)]
[!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CPP/ca2227-collection-properties-should-be-read-only_1.cpp)]

## <a name="related-rules"></a>Powiązane reguły

- [CA1819: Właściwości nie powinny zwracać tablic](../code-quality/ca1819-properties-should-not-return-arrays.md)