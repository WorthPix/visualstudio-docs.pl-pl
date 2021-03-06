---
title: Debuger nie może wyświetlić kodu źródłowego lub dezasemblacji | Dokumentacja firmy Microsoft
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
- disassembly code, errors
ms.assetid: 112d3ea3-fdd2-4bce-92b4-167a76258934
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2236a585c063194940cf505a0b1d225ae766e2a9
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49197889"
---
# <a name="debugger-cannot-display-source-code-or-disassembly"></a>Debuger nie może wyświetlić kodu źródłowego lub dezasemblacji
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Odczytuje ten błąd:  
  
 Debuger nie może wyświetlić kodu źródłowego lub dezasemblacji dla bieżącej lokalizacji, w którym wykonywanie zostało zatrzymane.  
  
 Ten komunikat o błędzie może wystąpić z kilku powodów:  
  
-   Możesz przekroczyć punkt przerwania w lokalizacji, dla których nie ma żadnych kodu źródłowego podczas debugowania języka, który nie obsługuje dezasemblacji. Otwórz **punktów przerwania** oknie zlokalizować punkt przerwania i usuń go.  
  
-   Jeśli debugujesz skryptu możesz przekroczyć punkt przerwania podczas, gdy nie było żadnych wątków w programach. Wybierz **kroku** lub **Kontynuuj** z **debugowania** menu, aby wznowić debugowanie.  
  
-   Zagadnienia dotyczące zabezpieczeń może uniemożliwić debugera na podstawie odczytu stosu, wątek, zarejestruj się i innymi informacjami kontekstu z programu, który debugujesz. Jest to najbardziej prawdopodobne w przypadku debugowania aplikacji sieci Web i nie mieć odpowiednich uprawnień dostępu do katalogu wirtualnego. Ustawienia zabezpieczeń katalogu wirtualnego na anonimowe i spróbuj ponownie.  
  
## <a name="see-also"></a>Zobacz też  
 [Podstawowe informacje o debugerze](../debugger/debugger-basics.md)   
 [Debugowanie w programie Visual Studio](../debugger/debugging-in-visual-studio.md)   
 [Wyświetlanie danych w debugerze](../debugger/viewing-data-in-the-debugger.md)



