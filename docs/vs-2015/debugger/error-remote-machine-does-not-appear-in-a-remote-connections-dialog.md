---
title: 'Błąd: Komputer zdalny nie jest wyświetlana w oknie dialogowym połączeń zdalnych | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
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
ms.assetid: 5fd98a5b-2cf3-4438-8b0f-6f1a742a62ce
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 552be1e38cdb7401af36b287b23091d754c35980
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685950"
---
# <a name="error-remote-machine-does-not-appear-in-a-remote-connections-dialog"></a>Błąd: Komputer zdalny nie jest wyświetlana w oknie dialogowym połączeń zdalnych
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [błąd: komputer zdalny nie jest wyświetlana w oknie dialogowym połączeń zdalnych](https://docs.microsoft.com/visualstudio/debugger/error-remote-machine-does-not-appear-in-a-remote-connections-dialog).  
  
Jeśli komputer zdalny nie zostanie wyświetlony w oknie dialogowym połączeń zdalnych, sprawdź następujące typowe przyczyny.  
  
 Jeśli używasz trybu zgodności zarządzanej, sprawdź w dokumentacji programu Visual Studio 2010: [Rozwiązywanie problemów z zdalne debugowanie — program Visual Studio 2010](https://msdn.microsoft.com/library/2ys11ead\(v=vs.100\).aspx) .  
  
### <a name="common-causes-for-this-error"></a>Typowe przyczyny tego błędu  
  
-   Komputer zdalny jest uruchomiona na komputerze, na którym znajduje się w innej podsieci. Aby rozwiązać ten problem, ręcznie wpisać nazwę lub adres IP w oknie dialogowym kwalifikatora  
  
-   Zdalny debuger nie jest uruchomiona na komputerze zdalnym. Aby rozwiązać ten problem, uruchom zdalny debuger.  
  
-   Zapora blokuje komunikację między Visual Studio i komputera zdalnego. Aby rozwiązać ten problem, Skonfiguruj zaporę, aby umożliwić komunikowania się programu Visual Studio i zdalny debuger (msvsmon).  
  
-   Oprogramowanie antywirusowe blokuje komunikację między Visual Studio i komputera zdalnego. Aby rozwiązać ten problem, należy skonfigurować oprogramowanie antywirusowe, aby zezwolić na program Visual Studio i zdalny debuger (msvsmon), do komunikowania się.  
  
## <a name="see-also"></a>Zobacz też  
 [Konfigurowanie narzędzi zdalnych na urządzeniu](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)


