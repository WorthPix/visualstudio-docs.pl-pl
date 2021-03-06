---
title: 'Porady: tłumienie ostrzeżeń przy użyciu elementu Menu | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- warnings, suppressing
- code analysis, suppressing warnings
ms.assetid: 36bd1850-dcde-4ed0-9bc3-0b83df434362
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1c756a5ab6516d78f5370622555898c98658e8b3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49211792"
---
# <a name="how-to-suppress-warnings-by-using-the-menu-item"></a>Porady: tłumienie ostrzeżeń przy użyciu elementu menu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

UWAGA]
>  W źródle pomijanie nie jest obsługiwana dla projektów witryny sieci web.  
  
 Okno analizy kodu na pomijanie ostrzeżeń analizy kodu. Pomijanie ostrzeżenie nie jest taka sama jak wyłączenie go. Gdy możesz pominąć ostrzeżenia, ma zastosowanie tylko do konkretnego wystąpienia naruszenia. Inne naruszenia tego samego ostrzeżenia nadal będą raportowane w oknie Lista błędów.  
  
 Po uruchomieniu analizy kodu, można określić, że jeden lub więcej ostrzeżeń analizy kodu, które są wyświetlane w oknie analizy kodu nie mają zastosowania do aplikacji. Na przykład można określić, czy kod jest poprawna, ponieważ jest. Lub może być tak, że niektóre naruszeń są — niski priorytet, a nie zostanie rozwiązany w bieżącym cyklu tworzenia oprogramowania. Niezależnie od przyczyny jest często przydatny wskazać, że ostrzeżenie nie ma zastosowania aby umożliwić członkom zespołu, wiadomo, że kod został zrecenzowany i ustalenie, czy można pominąć to ostrzeżenie. W źródle pomijania jest przydatne, ponieważ dzięki temu można umieścić pomijanie blisko której generowane jest ostrzeżenie.  
  
 Możesz wybrać, czy pomijanie pojawi się w kodzie źródłowym lub w pliku pominięć globalnych. Niektóre pominięcia muszą być umieszczone w pliku pominięć globalnych. Jeśli tak, jest **w źródłowej** opcja zostanie wyłączona.  
  
### <a name="to-suppress-a-warning-by-using-menu-item"></a>Aby pominąć ostrzeżenie przy użyciu elementu menu  
  
1.  Na **analizy** menu, wybierz **Windows** , a następnie wybierz **analizy kodu**.  
  
2.  W **analizy kodu** okna, wybierz opcję Pomiń ostrzeżenia.  
  
3.  Wybierz akcje, a następnie wybierz **Pomijaj komunikaty**, a następnie wybierz **w źródłowej** lub **w pliku pominięć projektu**.  
  
     Pomijane jest szczególne ostrzeżenie i ostrzeżenie jest wyświetlane w oknie analizy kodu za pomocą przekreślenia.  
  
> [!NOTE]
>  Ograniczeń, które nie mają na celu pojawiają się w pliku pominięć globalnych.



