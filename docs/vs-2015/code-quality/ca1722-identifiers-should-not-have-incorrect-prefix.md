---
title: 'CA1722: Identyfikatory nie powinny mieć niepoprawnego prefiksu | Dokumentacja firmy Microsoft'
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
- IdentifiersShouldNotHaveIncorrectPrefix
- CA1722
helpviewer_keywords:
- CA1722
- IdentifiersShouldNotHaveIncorrectPrefix
ms.assetid: c3313c51-d004-4f9a-a0d1-6c4c4a1fb1e6
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 305e0f251ee64165a9a25481aa6c45299d888b33
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49215595"
---
# <a name="ca1722-identifiers-should-not-have-incorrect-prefix"></a>CA1722: Identyfikatory powinny mieć poprawny prefiks
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectPrefix|
|CheckId|CA1722|
|Kategoria|Microsoft.Naming|
|Zmiana kluczowa|Kluczowa|

## <a name="cause"></a>Przyczyna
 Identyfikator ma niepoprawny prefiks.

## <a name="rule-description"></a>Opis reguły
 Zgodnie z konwencją, tylko niektóre elementy programowania mają nazwy rozpoczynające się od określonego prefiksu.

 Nazwy typów nie ma określonego prefiksu i nie powinien być poprzedzony "C". Ta zasada zgłasza naruszenia nazwy typów, takich jak "CMyClass" i nie raportuje naruszenia nazwy typów, takich jak "Pamięci podręcznej".

 Konwencje nazewnictwa Obejmij wygląd wspólnych bibliotek obiektu docelowego środowiska uruchomieniowego języka wspólnego. Zmniejsza to nauki, jest wymagany dla nowe biblioteki oprogramowania, która zwiększa poziom zaufania klientów, że biblioteka został opracowany przez osobę, która ma doświadczenie w tworzenie kodu zarządzanego.

## <a name="how-to-fix-violations"></a>Jak naprawić naruszenia
 Usuń prefiks z identyfikatorem.

## <a name="when-to-suppress-warnings"></a>Kiedy pominąć ostrzeżenia
 Nie pomijaj ostrzeżeń dla tej reguły.

## <a name="related-rules"></a>Powiązane reguły
 [CA1715: Identyfikatory powinny mieć poprawny prefiks](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)



