---
title: 'CA2140: Kod przezroczysty nie może odwoływać się elementów krytycznych dla zabezpieczeń | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2129
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2140
helpviewer_keywords:
- CA2140
- SecurityTransparentCodeShouldNotReferenceNonpublicSecurityCriticalCode
- CA2129
ms.assetid: 251a12da-0557-47f5-a4f7-0229d590ae7b
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 16d7ba9c5bac34d92e0141d9ef0fda9b41368876
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49201243"
---
# <a name="ca2140-transparent-code-must-not-reference-security-critical-items"></a>CA2140: Jawny kod nie może odwoływać się do elementów krytycznych dla zabezpieczeń
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|TypeName|TransparentMethodsMustNotReferenceCriticalCode|
|CheckId|CA2140|
|Kategoria|Microsoft.Security|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Metoda przezroczysty.

-   obsługuje typ wyjątków krytycznych zabezpieczeń

-   ma parametr, który jest oznaczony jako typu krytycznego dla zabezpieczeń

-   ma parametr ogólny z ograniczeniami krytyczne zabezpieczeń

-   ma zmiennej lokalnej typu krytycznego dla zabezpieczeń

-   odwołuje się do typu, która jest oznaczona jako zabezpieczeń krytycznych

-   wywołuje metodę, która jest oznaczona jako zabezpieczeń krytycznych

-   odwołuje się do pola, która jest oznaczona jako zabezpieczeń krytycznych

-   Zwraca typ, który jest oznaczony jako zabezpieczeń krytycznych

## <a name="rule-description"></a>Opis reguły
 Element kodu, który jest oznaczony za pomocą <xref:System.Security.SecurityCriticalAttribute> atrybutu jest krytyczny dla bezpieczeństwa. Przezroczysta metoda nie może użyć elementu krytycznego dla zabezpieczeń. Jeśli przezroczysty typ próbuje użyć typu krytycznego dla zabezpieczeń <xref:System.TypeAccessException>, <xref:System.MethodAccessException> , lub <xref:System.FieldAccessException> jest wywoływane.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Aby naprawić naruszenie tej zasady, wykonaj jedną z następujących czynności:

-   Oznacz element kodu, który korzysta z kodu krytycznego zabezpieczeń za pomocą <xref:System.Security.SecurityCriticalAttribute> atrybutu

     \- lub —

-   Usuń <xref:System.Security.SecurityCriticalAttribute> atrybut od elementów kodu, które są oznaczone jako zabezpieczeń krytycznych i zamiast tego oznacz je za pomocą <xref:System.Security.SecuritySafeCriticalAttribute> lub <xref:System.Security.SecurityTransparentAttribute> atrybutu.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="example"></a>Przykład
 W poniższych przykładach metoda przezroczysta pod względem próbuje odwołania zabezpieczeń krytycznych kolekcji ogólnych, zabezpieczeń krytycznych pola i metody krytycznej zabezpieczeń.

 [!code-csharp[FxCop.Security.CA2140.TransparentMethodsMustNotReferenceCriticalCode#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2140.transparentmethodsmustnotreferencecriticalcode/cs/ca2140 - transparentmethodsmustnotreferencecriticalcode.cs#1)]

## <a name="see-also"></a>Zobacz też
 <xref:System.Security.SecurityTransparentAttribute><xref:System.Security.SecurityCriticalAttribute>
 <xref:System.Security.SecurityTransparentAttribute>
 <xref:System.Security.SecurityTreatAsSafeAttribute>
 <xref:System.Security?displayProperty=fullName>



