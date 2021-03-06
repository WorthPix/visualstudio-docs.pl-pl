---
title: Plik wykonywalny dla sesji, okno dialogowe debugowania | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.exefordebug
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- executable files, specifying when debugging
- DLLs, debugging
- debugger, Executable for Debugging Session dialog box
- Executable for Debugging Session dialog box
ms.assetid: c0ddbe32-b99f-4425-acf1-f48842804f56
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2d1279ba5b3ed79c4115143a72e4543bbd6c123d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49189829"
---
# <a name="executable-for-debugging-session-dialog-box"></a>Wykonywalny dla sesji debugowania — Okno dialogowe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

To okno dialogowe pojawia się podczas próby debugowania biblioteki DLL dla których nie pliku wykonywalnego jest określony. Program Visual Studio nie można uruchomić biblioteki DLL bezpośrednio. Zamiast tego uruchomi określony plik wykonywalny. Można debugować biblioteki DLL, gdy jest wywoływana przez plik wykonywalny.  
  
 **Nazwa pliku wykonywalnego**  
 Wprowadź ścieżkę do pliku wykonywalnego, który wywołuje bibliotekę DLL debugowania.  
  
 **Adres URL, których projekt może być używane (tylko serwery ATL)**  
 Jeśli debugujesz ATL DLL serwera, wprowadź adres URL, gdzie można znaleźć projektu.  
  
 Po wprowadzeniu, te ustawienia są przechowywane w projekcie strony właściwości, dzięki czemu nie musisz wprowadzać ich ponownie udział podczas kolejnych sesji debugowania. Jeśli potrzebujesz zmienić ustawienia, można otwierać strony właściwości i zmienić wartości. Aby uzyskać więcej informacji na temat określania plik wykonywalny dla sesji debugowania, zobacz [debugowania bibliotek DLL](../debugger/how-to-debug-native-dlls.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Debugowanie w programie Visual Studio](../debugger/debugging-in-visual-studio.md)



