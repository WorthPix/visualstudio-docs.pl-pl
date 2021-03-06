---
title: 'Porady: eksport cieniowania'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 0bd48bf4-9792-4456-a545-e462a2be668d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bd06664cda1c60d2624b77a0381e1269fcb3c484
ms.sourcegitcommit: 25fc9605ba673afb51a24ce587cf4304b06aa577
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2018
ms.locfileid: "47028979"
---
# <a name="how-to-export-a-shader"></a>Porady: eksport cieniowania

W tym artykule przedstawiono sposób użycia **Shader Designer** wyeksportować modułu cieniującego kierowane wykres modułu cieniującego języka (DGSL) służy w swojej aplikacji.

## <a name="export-a-shader"></a>Eksportowanie cieniowania

Po utworzeniu modułu cieniującego, przy użyciu narzędzia Projektant programu do cieniowania i przed użyciem w swojej aplikacji, należy go wyeksportować w formacie, który rozumie interfejsu API grafiki. Możesz wyeksportować modułu cieniującego na różne sposoby do potrzeb różnych.

1. W programie Visual Studio, otwórz **wizualny wykres modułu cieniującego (.dgsl)** pliku.

     Jeśli nie masz **wizualny wykres modułu cieniującego (.dgsl)** plik, aby otworzyć, utwórz je, zgodnie z opisem w [porady: tworzenie cieniowania koloru podstawowego](../designers/how-to-create-a-basic-color-shader.md).

2. Na **Shader Designer** narzędzi, wybierz **zaawansowane** > **wyeksportować** > **Eksportuj jako**. **Eksportowania modułu cieniującego** pojawi się okno dialogowe.

3. W **Zapisz jako typ** listy rozwijanej wybierz format, który chcesz wyeksportować.

     Poniżej przedstawiono formaty, które można wybrać:

     **Program do cieniowania pikseli HLSL (\*.hlsl)** eksportuje programu do cieniowania w postaci kodu źródłowego wysokiej Level Shader Language (HLSL). Ta opcja umożliwia później zmodyfikować cieniowanie tak, nawet w przypadku, po jej wdrożeniu w aplikacji. To może ułatwić debugowanie i poprawki kodu, w oparciu problemy użytkowników końcowych, ale również ułatwia użytkownikowi modyfikowanie modułu cieniującego niechciane — na przykład, aby uzyskać nienależną przewagę w grze przewagę. Ponadto może to zwiększyć czas ładowania modułu cieniującego.

     **Skompilowany program do cieniowania pikseli (\*.cso)** eksportuje programu do cieniowania w postaci kodu bajtowego języka HLSL. Ta opcja umożliwia później zmodyfikować cieniowanie tak, nawet w przypadku, po jej wdrożeniu w aplikacji. To może ułatwić debugowanie i poprawki kodu, w oparciu problemy użytkowników końcowych, ale ponieważ programu do cieniowania jest wstępnie skompilowanym, go nie są naliczane dodatkowe środowiska uruchomieniowego obciążenie podczas ładowania programu do cieniowania za pomocą aplikacji. Wystarczająco doświadczeni użytkownicy mogą modyfikować programu do cieniowania w sposób niepożądane, ale kompilowanie programu do cieniowania sprawia, że to znacznie trudniejsze.

     **Nagłówek języka C++ (\*.h)** eksportuje programu do cieniowania jako nagłówek stylu C, który definiuje tablica bajtów, która zawiera kod bajtowy HLSL. Tej opcji można tworzyć bardziej czasochłonne debugować i poprawki kodu, w oparciu problemy użytkowników końcowych, ponieważ aplikacja musi ponownie skompilowana, aby przetestować poprawki. Jednak ponieważ dzięki temu jest trudne, chociaż nie jest to niemożliwe, aby zmodyfikować cieniowanie tak, po jej wdrożeniu w aplikacji, stanowi trudności w większości użytkownikowi, który chce się zmodyfikować cieniowanie tak, w sposób niepożądane.

4. W **nazwy pliku** pola kombi, określ nazwę dla eksportowanego programu do cieniowania, a następnie wybierz **Zapisz** przycisku.

## <a name="see-also"></a>Zobacz także

- [Instrukcje: tworzenie cieniowania koloru podstawowego](../designers/how-to-create-a-basic-color-shader.md)
- [Projektant cieniowania](../designers/shader-designer.md)