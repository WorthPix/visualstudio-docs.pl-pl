---
title: Za pomocą wyrażeń regularnych w programie Visual Studio | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vsregularexpressionhelp
- vs.regularexpressionhelp
- vs.wildcardsbuilder
- vs.netregularexpressionhelp
- vs.wildcards
helpviewer_keywords:
- regular expressions [Visual Studio]
- regular expressions
- Visual Studio, regular expressions
ms.assetid: 718a617d-0e05-47e1-a218-9746971527f4
caps.latest.revision: 56
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4edf0add3e29dd7fe4156a220fe0edc60e47f117
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49285470"
---
# <a name="use-regular-expressions-in-visual-studio"></a>Używanie wyrażeń regularnych w programie Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
Visual Studio używa regularnego wyrażenia .NET Framework do znajdowania i zamieniania tekstu. Aby uzyskać więcej informacji o wyrażeniach regularnych programu .NET, zobacz [wyrażeń regularnych programu .NET Framework](http://msdn.microsoft.com/library/521b3f6d-f869-42e1-93e5-158c54a6895d).

Przed Visual Studio 2012 Visual Studio używał niestandardowych składni wyrażeń regularnych w oknach Znajdź i Zamień. Zobacz [Visual Studio regularne wyrażenia konwersje](https://msdn.microsoft.com/library/2k3te2cs\(v=vs.110\).aspx) objaśnienia dotyczące jak konwertować niektóre częściej używane niestandardowe znaki regularnych wyrażeń do wersji platformy .NET.

> [!TIP]
> W systemach operacyjnych Windows większość linii kończyć się "\r\n" (znak powrotu karetki następuje nowy wiersz). Następujące znaki nie są widoczne, ale są obecne w edytorze i są przekazywane do usługi .NET Regular Expression.

> [!TIP]
> Aby uzyskać informacje o wyrażeniach regularnych, które są używane we wzorcach zamieniania, zobacz [podstawienia](http://msdn.microsoft.com/library/d1f52431-1c7d-4dc6-8792-6b988256892e). Aby użyć grupy numerowanych przechwytywania, składnia jest `$1` Aby określić numerowaną grupę i `(x)` do określenia danej grupie. Na przykład zgrupowanych wyrażenia regularnego `(\d)([a-z])` znajduje cztery dopasowań w następujący ciąg: **1a 2b 3c 4d**. Ciąg zastępujący `z$1` konwertuje ciąg na **z1 z2 z3 z4**.

## <a name="regular-expression-examples"></a>Przykłady wyrażeń regularnych

Oto kilka przykładów:

|Cel|Wyrażenie|Przykład|
|-------------|----------------|-------------|
|Dopasuj jeden dowolny znak (oprócz podziału wiersza)|.|`a.o` pasuje "aro" w "around" i "abo" w "about" ale nie "acro" w "w".|
|Dopasowuje zero lub więcej wystąpień poprzedniego wyrażenia (dopasowuje tak dużą liczbę znaków, jak to możliwe)|*|`a*r` pasuje "r" w "rack", "ar" w "ark" i "aar" w "aardvark"|
|Dopasowuje dowolny znak zero lub więcej razy (symbol wieloznaczny *)|.*|c.*e pasuje do "cke" w "racket", "comme" w "comment" i "code" w "code"|
|Pasuje jedno lub więcej wystąpień poprzedniego wyrażenia (dopasowuje tak dużą liczbę znaków, jak to możliwe)|+|`e.+e` pasuje do "eede" w "feeder" ale nie "ee".|
|Dopasowuje dowolny znak jeden lub więcej razy (symbol wieloznaczny?)|.+|e. + e pasuje do "eede" w "feeder" ale nie "ee".|
|Dopasowuje zero lub więcej wystąpień poprzedniego wyrażenia (dopasowuje tak małą znaków, jak to możliwe)|*?|`e.*?e` pasuje do "ee" w "feeder" ale nie do "eede".|
|Pasuje jedno lub więcej wystąpień poprzedniego wyrażenia (dopasowuje tak małą znaków, jak to możliwe)|+?|`e.+?e` pasuje "do ente" i "erprise" w "enterprise", ale nie całego słowa "enterprise".|
|Zakotwiczenia ciągu dopasowania do początku wiersza lub ciągu|^|`^car` Dopasowuje słowa "samochód" tylko wtedy, gdy pojawia się na początku wiersza.|
|Zakotwiczenia ciągu dopasowania na końcu wiersza|\r?$|`End\r?$` pasuje do "end" tylko wtedy, gdy pojawia się na końcu wiersza.|
|Dopasuj jeden dowolny znak, które są dostępne w zestawie|[abc]|`b[abc]` pasuje do "ba", "bb" i "bc".|
|Dopasuj dowolny znak zakresu znaków|[a-f]|`be[n-t]` Dopasowuje "bet" w "between", "ben" w "beneath" i "bes" w "beside", ale nie "below".|
|Przechwytywanie i niejawne numerowanie wyrażenia zawartgoe w nawiasach|()|`([a-z])X\1` pasuje "do aXa" i "bXb", ale nie "aXb". ". "\1" odnosi się do pierwszej grupy wyrażenie "[a-z]".|
|Unieważnienie dopasowania|(?! ABC)|`real (?!ity)` pasuje do członu "real" w słowach "realty" i "really", ale nie w "reality". W "realityreal" danych znajdzie także drugi "prawdziwy" (ale nie pierwszy "prawdziwy").|
|Dopasowuje dowolny znak, który nie znajduje się w danym zestawie znaków|[^ abc]|`be[^n-t]` pasuje "do bef" w "przed", "beh" w "za" i "bel" w "below", ale nie "beneath".|
|Dopasowuje wyrażenie przed lub po symbolu.|&#124;|`(sponge&#124;mud) bath` pasuje "sponge bath" i "mud bath."|
|Uniknij znaku następującej odwróconej kreski ukośnej|\|`\^` pasuje do znaku ^.|
|Określ liczbę wystąpień poprzedzającego znaku lub grupy|{x},, gdzie x jest liczbą wystąpień|`x(ab){2}x` odpowiada "xababx" i `x(ab){2,3}x` odpowiada "xababx" i "xabababx", ale nie "xababababx".|
|Dopasowuje tekst w klasie znaku Unicode, gdzie "X" jest numerem kodu Unicode. Aby uzyskać więcej informacji dotyczących klas znaków Unicode zobacz<br /><br /> [Właściwości znaków standardu Unicode 5.2](http://www.unicode.org/versions/Unicode5.2.0/ch04.pdf).|\p{X}|`\p{Lu}` pasuje do "T" i "D" w "Thomas Doe".|
|Dopasuj granicę wyrazu|`\b` (Poza klasą znak \b Określa granicy słowa i wewnątrz znak klasy określa backspace).|`\bin` pasuje do "w" w "wewnątrz" ale nie "pinto".|
|Dopasowuje znak końca wiersza (czyli znak powrotu karetki następuje nowy wiersz).|\r?\n|`End\r?\nBegin` pasuje do "Koniec" i "Początek" tylko wtedy, gdy "Koniec" jest ostatnim ciągiem w wierszu a "Początek" jest pierwszym ciągiem w następnym wierszu.|
|Pasuje do dowolnego znaku alfanumerycznego|\w|`a\wd` Dopasowuje "add" i "a1d" ale nie "d".|
|Dopasowuje dowolny biały znak.|(? ([^ \r\n])\s)|`Public\sInterface` pasuje do frazy "Interfejs publiczny".|
|Dopasuj dowolną cyfrę|\d|`\d` pasuje i "3" w "3456", "2" w 23" i"1"w"1".|
|Dopasowuje znak Unicode|\uXXXX gdzie XXXX określa wartość znaku Unicode.|`\u0065` Dopasowuje znak "e".|
|Dopasuj identyfikator|\b(_\w+&#124;[\w-[0-9\_]]\w*)\b|Dopasowuje "type1", ale nie & type1 "lub" #define ".|
|Dopasuj ciąg w cudzysłowie|((\\".+?\\")&#124;('.+?'))|Dopasowuje dowolny ciąg w pojedynczym lub podwójnym cudzysłowie.|
|Dopasuj liczbę szesnastkową|\b0[xX]([0-9a-fA-F]\)\b|Dopasowuje "0xc67f", ale nie "0xc67fc67f".|
|Dopasuj liczby całkowite i miejsca dziesiętne|\b[0-9]*\\.\*[0-9]+\b|Dopasowuje "1,333".|