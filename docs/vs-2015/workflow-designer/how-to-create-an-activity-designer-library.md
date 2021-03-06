---
title: 'Porady: Tworzenie biblioteki projektanta działań | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 5b62e092-63b3-462d-9d77-fb112482f45d
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 6802f92f349d15d48935f4e7c3db85abf7c12535
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49258274"
---
# <a name="how-to-create-an-activity-designer-library"></a>Porady: Tworzenie biblioteki projektanta działań
Niestandardowi Projektanci działań umożliwiają tworzenie interfejsu użytkownika dla standardowego lub niestandardowego działania. Kontrolowania złożoności interfejsu użytkownika i mieć możliwość utworzenia więcej niż jeden projektanta działań dla działania. Ten scenariusz umożliwia tworzenie projektantów, które są dostosowane do wielu odbiorców.  
  
### <a name="to-create-an-activity-designer-library"></a>Aby utworzyć biblioteki projektanta działań  
  
1.  Rozpocznij [!INCLUDE[vs2010](../includes/vs2010-md.md)].  
  
2.  Na **pliku** menu wskaż **New**, a następnie wybierz pozycję **projektu...** Aby otworzyć **nowy projekt** okno dialogowe.  
  
3.  W **typów projektów** okienku wybierz **przepływu pracy** albo **Visual C#** lub **języka Visual Basic** grupowania w zależności od preferowanego język.  
  
4.  W **szablony** okienku wybierz **Biblioteka projektanta działań**.  
  
5.  W **nazwa** wprowadź opisową nazwę projektu ułatwić identyfikowanie.  
  
6.  W **lokalizacji** wprowadź katalog, w którym chcesz zapisać projekt, lub kliknij przycisk **Przeglądaj** można przejść do niego.  
  
7.  W **rozwiązania** polu, wpisz nazwę opisową dla danego rozwiązania, a następnie kliknij przycisk **OK**.  
  
    > [!NOTE]
    >  Jeśli chcesz dodać aplikację konsoli przepływu pracy do istniejącego rozwiązania, otwórz rozwiązanie w [!INCLUDE[vs2010](../includes/vs2010-md.md)], kliknij prawym przyciskiem myszy rozwiązanie w **Eksploratora rozwiązań**i wybierz **Dodaj**, a następnie **Nowy projekt...** Aby otworzyć **nowy projekt** okno dialogowe. Należy postępować zgodnie z powyższym opisem w tej procedurze.  
  
8.  Szablon projektu tworzy definicji działania projektanta XAML i kodem pliku implementacji w kodzie źródłowym. [!INCLUDE[wfd1](../includes/wfd1-md.md)] Otwiera i wyświetla kanwy dla projektanta działań.  
  
9. Przeciągnij [!INCLUDE[avalon1](../includes/avalon1-md.md)] kontrolki z **przybornika** do powierzchni projektu, który z nich korzystać w swojej niestandardowego projektanta działań.  Na przykład sposób implementacji niestandardowego projektanta działań zobacz [porady: Tworzenie niestandardowego projektanta działań](http://msdn.microsoft.com/library/2f3aade6-facc-44ef-9657-a407ef8b9b31).  
  
    > [!WARNING]
    >  Niestandardowi Projektanci działań może służyć do niestandardowych działań, jak również jak w przypadku domyślnej [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)]działań.  
  
## <a name="see-also"></a>Zobacz też  
 [Tworzenie projektu przepływu pracy](../workflow-designer/creating-a-workflow-project.md)