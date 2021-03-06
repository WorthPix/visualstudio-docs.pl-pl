---
title: Jak można debugować funkcje API systemu Windows? | Microsoft Docs
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
- vs.debug.api
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], Windows API functions
- NT symbols and debugging Windows API functions
- Windows API functions, debugging
- Windows API, debugging API functions
- APIs, debugging
ms.assetid: 7c126f57-62ab-4d94-9805-632d696ba1f0
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 09885a056f075a771fd034830ce15a516d2520f2
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49176721"
---
# <a name="how-can-i-debug-windows-api-functions"></a>Jak można debugować funkcje API systemu Windows?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Jeśli chcesz debugować funkcja interfejsu API Windows, która zawiera symbole NT załadowane, wykonaj następujące czynności.  
  
### <a name="to-set-a-breakpoint-on-a-windows-api-function-with-nt-symbols-loaded"></a>Aby ustawić punkt przerwania w funkcji Windows API z symbole NT załadowane  
  
-   Podaj nazwę funkcji wraz z nazwą biblioteki DLL, w której znajduje się funkcja. W 32-bitowego kodu formularz dekorowane nazwy funkcji. Aby ustawić punkt przerwania na **MessageBeep**, na przykład, należy wprowadzić następujące czynności.  
  
    ```  
    {,,USER32.DLL}_MessageBeep@4  
    ```  
  
     Aby uzyskać nazwę z atrybutami, zobacz [wyświetlania nazw Ozdobionych](http://msdn.microsoft.com/en-us/f79e2717-a4db-4d12-a689-69830cce2be0).  
  
## <a name="see-also"></a>Zobacz też  
 [Debugowanie kodu natywnego — często zadawane pytania](../debugger/debugging-native-code-faqs.md)   
 [Debugowanie kodu natywnego](../debugger/debugging-native-code.md)



