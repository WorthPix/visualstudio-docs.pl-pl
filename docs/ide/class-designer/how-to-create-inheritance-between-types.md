---
title: "Porady: Tworzenie dziedziczenia pomiędzy typami (Projektant klas) | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.classdesigner.inheritanceline
helpviewer_keywords:
- inheritance, relationship defining
- relationships, defining inheritance
ms.assetid: 3786a21c-8022-4bf5-9d13-740fd354e93c
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b939da3ae4020cc6412f9b1767d5bef8bce05472
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-inheritance-between-types-class-designer"></a>Porady: Tworzenie dziedziczenia pomiędzy typami (Projektant klas)
Aby utworzyć relację dziedziczenia między dwoma typami na diagramie klas, za pomocą projektanta klas, połączenie typu podstawowego z jego pochodny typ lub typy. Może mieć relację dziedziczenia między dwiema klasami, między klasą a interfejsem lub między dwa interfejsy.  
  
### <a name="to-create-an-inheritance-between-types"></a>Aby utworzyć dziedziczenia pomiędzy typami  
  
1.  Z projektu w Eksploratorze rozwiązań Otwórz plik diagramu (.cd) klasy.  
  
     Jeśli nie masz diagramu klas, należy go utworzyć. Zobacz [porady: Dodawanie diagramów klasy do projektów](how-to-add-class-diagrams-to-projects.md).  
  
2.  W **przybornika**w obszarze **Projektant klas**, kliknij przycisk **dziedziczenia**.  
  
3.  Na diagramie klas Rysowanie linii dziedziczenia pomiędzy typami, które mają, zaczynając od:  
  
    -   Klasa pochodna do klasy podstawowej  
  
    -   Klasa implementująca jak zaimplementowany interfejs  
  
    -   Rozszerzanie interfejs do rozszerzonego interfejsu  
  
4.  Opcjonalnie Jeśli typ pochodny od typu ogólnego, kliknij przycisk linii dziedziczenia. W **właściwości** ustaw **argumentów typu** właściwości pasuje do typu, który ma obowiązywać dla typu ogólnego.  
  
    > [!NOTE]
    >  Jeśli nadrzędnej klasy abstrakcyjnej zawiera co najmniej jeden abstrakcyjny element członkowski, wszystkie abstrakcyjne elementy członkowskie są zaimplementowane jako dziedziczące klasy nieabstrakcyjnej.  
    >   
    >  Mimo że można Wizualizuj istniejące typy ogólne, nie można utworzyć nowych typów ogólnych. Nie można zmienić również parametry typu dla istniejących typów ogólnych.  
  
## <a name="see-also"></a>Zobacz także
[Dziedziczenie](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)   
[Podstawowe informacje o dziedziczeniu](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)   
[Porady: wyświetlanie dziedziczenia pomiędzy typami](how-to-view-inheritance-between-types.md)   
[Klasy Visual C++ w Projektancie klas](visual-cpp-classes.md)