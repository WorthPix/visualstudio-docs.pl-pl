---
title: Oczekiwano &#39;]&#39; w wyrażeniu regularnym (JavaScript) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1ca2079a-44dd-479f-a1e3-e04a14d0739e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 64ef929ba309f0b496e72f3cf740daf6970d08fb
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283720"
---
# <a name="expected-3939-in-regular-expression-javascript"></a>Oczekiwano &#39;]&#39; w wyrażeniu regularnym (JavaScript)
Podjęto próbę utworzenia klasy znaków dopasowania wyrażenia regularnego, ale nie zawiera nawias zamykający. Pojedynczy znak literału kombinacje mogą być włączane do klasy znaków w, umieszczając je w nawiasach. Klasa znaków dopasowuje dowolny znak zawartych w nim. Na przykład / [abc] / pasuje do dowolnej litery "a", "b", lub "c".  
  
### <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Dodaj prawy nawias kwadratowy do wyrażenia regularnego.  
  
    > [!NOTE]
    >  Jeśli chcesz dopasować pojedynczy nawias, zmienić jego znaczenie znakiem kreski ułamkowej odwróconej - \\[— tak nie jest interpretowany jako znak specjalny przez [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].  
  
## <a name="see-also"></a>Zobacz też  
 [Obiekt będący wyrażeniem regularnym](../../javascript/reference/regular-expression-object-javascript.md)   
 [Składnia wyrażeń regularnych (JavaScript)](https://msdn.microsoft.com/library/1400241x)