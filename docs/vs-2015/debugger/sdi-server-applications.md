---
title: Aplikacje serwera SDI | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- SDI server applications
- SDI server applications, debugging
ms.assetid: 09713718-1376-4753-b119-26f36639693e
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba975d21e1fbef2d32b45dd4ebdc758e8b6cf575
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49199072"
---
# <a name="sdi-server-applications"></a>Aplikacje serwera SDI
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Jeśli debugujesz aplikację serwera SDI, należy określić `/Embedding` lub `/Automation` w **argumenty wiersza polecenia** właściwość *projektu* okno dialogowe strony właściwości dla C/C++, C#, lub Projekty języka Visual Basic.  
  
 Za pomocą tych argumentów wiersza polecenia debugera można uruchomić aplikacji serwera, tak, jakby zostały uruchomione z kontenera. Uruchamianie kontenera za pomocą Menedżera programu lub Menedżer plików następnie spowoduje, że kontener, aby użyć wystąpienia programu server uruchomiony w debugerze.  
  
## <a name="finding-the-command-line-arguments-property"></a>Wyszukiwanie właściwości argumenty wiersza polecenia  
 Aby uzyskać dostęp do *projektu* okno dialogowe strony właściwości, kliknij prawym przyciskiem myszy projekt w Eksploratorze rozwiązań, a następnie z menu skrótów wybierz polecenie Właściwości. Aby znaleźć właściwości argumenty wiersza polecenia, rozwiń kategorię właściwości konfiguracji, a następnie kliknij przycisk na stronie debugowanie.  
  
## <a name="see-also"></a>Zobacz też  
 [COM i debugowanie ActiveX](../debugger/com-and-activex-debugging.md)   
 [Instrukcje: debugowanie serwerów COM](../debugger/how-to-debug-com-servers.md)



