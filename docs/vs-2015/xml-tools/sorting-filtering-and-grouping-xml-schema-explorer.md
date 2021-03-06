---
title: Sortowanie, filtrowanie i grupowanie (Eksplorator schematu XML) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a914de0-9ffc-4526-9603-92e460e52513
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 49bd65d0ca9be83665f5f364f5e1f2115279cf5c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49229739"
---
# <a name="sorting-filtering-and-grouping-xml-schema-explorer"></a>Sortowanie, filtrowanie i grupowanie (Eksplorator schematu XML)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
W tym temacie opisano opcje, które są dostępne za pośrednictwem **opcje grupowanie, filtrowanie i sortowanie** menu na pasku narzędzi Eksploratora schematu XML.  
  
## <a name="filter-options"></a>Opcje filtru  
 Dostępne są następujące opcje filtru. Domyślnie **Pokaż przestrzenie nazw** i **Pokaż pliki schematu** są zaznaczone opcje.  
  
-   **Pokaż przestrzenie nazw**.  
  
-   **Pokaż pliki schematu**.  
  
-   **Pokaż Kompozytory (sekwencji/wyboru/all)**.  
  
## <a name="sorting-options"></a>Opcje sortowania  
 Dostępne są następujące opcje sortowania. Wartość domyślna to **sortowania według typu**. Sortuj według opcji nie dotyczą plików i przestrzeni nazw.  
  
-   **Sortuj według typu**.  
  
-   **Sortuj według nazwy**.  
  
-   **Dokumentowanie kolejności**.  
  
### <a name="sort-by-type"></a>Sortuj według typu  
 Gdy **sortowania według typu** opcja jest zaznaczona, globalne węzły są sortowane w następującej kolejności. Węzły są posortowane alfabetycznie w każdej grupie.  
  
1.  `import` węzły.  
  
2.  `include` węzły.  
  
3.  `redefine` węzły.  
  
4.  `attribute` węzły.  
  
5.  `attributeGroup` węzły.  
  
6.  `complexType` węzły.  
  
7.  `simpleType` węzły.  
  
8.  `element` węzły.  
  
9. `group` węzły.  
  
### <a name="sort-by-name"></a>Sortuj według nazwy  
 Gdy **Sortuj według nazwy** opcja jest zaznaczona, globalne węzły są sortowane w następującej kolejności:  
  
1.  `import` węzły (w kolejności alfabetycznej według przestrzeni nazw).  
  
2.  `include` węzły (w kolejności alfabetycznej według `schemaLocation` atrybutów).  
  
3.  `redefine` węzły (w kolejności alfabetycznej według `schemaLocation` atrybutów).  
  
4.  Inne węzły globalne w kolejności alfabetycznej.  
  
### <a name="document-order"></a>Kolejności dokumentu  
 **Kolejności dokumentu** opcja jest dostępna, gdy **Pokaż pliki schematu** opcja jest zaznaczona. Gdy **kolejności dokumentu** jest zaznaczone, globalne węzły są wyświetlane w kolejności, w jakiej występują w pliku schematu.  
  
## <a name="persisting-sortfilter-options"></a>Utrwalanie opcje sortowania/filtrowania  
 Sortowanie, filtrowanie i grupowanie opcje są zapisywane w rejestrze dla każdego użytkownika, niezależnie od tego, które rozwiązanie lub pliki były otwarte podczas ustawienia zostały zmienione.





