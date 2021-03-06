---
title: 'Diagramy składników UML: Odwołanie | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.teamarch.componentdiagram.diagram
- vs.teamarch.componentdiagram.toolbox
- vs.teamarch.UMLModelExplorer.componentdiagram
helpviewer_keywords:
- UML diagrams, component
- diagrams - modeling, component
- diagrams - modeling, UML component
- UML, component diagrams
- component diagrams
ms.assetid: 5eddff6a-892a-4c3c-9278-687ac1eccc50
caps.latest.revision: 38
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: b99188aa069a830d17e31733ad20b0ae727d63f9
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49206744"
---
# <a name="uml-component-diagrams-reference"></a>Diagramy składników UML: Odwołanie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

W programie Visual Studio *diagram składników* pokazuje części projektu dla systemu oprogramowania. Diagram składników pomaga wizualizować strukturę wysokiego poziomu systemu i zachowanie usługi, które te elementy zapewniają i wykorzystują za pośrednictwem interfejsów. Aby utworzyć diagram składników UML na **architektury** menu, kliknij przycisk **nowe UML lub diagramu warstwowego**.  
  
 Aby zobaczyć, które wersje programu Visual Studio obsługuje tę funkcję, zobacz [obsługiwana wersja dla narzędzia architektury i modelowania](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Aby opisać projekt, który jest implementowany w dowolnym języku lub stylu, można użyć diagramu składników. Jest tylko niezbędne do identyfikowania części projektu, które współdziałają z innymi częściami projektu za pomocą ograniczonego zestawu danych wejściowych i wyjściowych. Składniki mogą być w dowolnej skali i mogą być połączone ze sobą w jakikolwiek sposób.  
  
 Aby uzyskać więcej informacji o sposobie używania diagramów składników w procesie projektowania, zobacz [modelowanie architektury aplikacji](../modeling/model-your-app-s-architecture.md).  
  
> [!NOTE]
>  W tym temacie opisano elementy, które można używać w diagramach składników. Aby uzyskać bardziej szczegółowe informacje o tym, jak Rysowanie diagramów składników zobacz [diagramy składników UML: wskazówki dotyczące](../modeling/uml-component-diagrams-guidelines.md). Aby uzyskać więcej informacji na temat narysować diagramy modelowania ogólnie rzecz biorąc, zobacz [modeli i diagramów UML Edytuj](../modeling/edit-uml-models-and-diagrams.md).  
  
## <a name="reading-component-diagrams"></a>Odczytywanie diagramów składników  
 W poniższej tabeli opisano elementy, które można użyć na diagramie składników, wraz z ich właściwości głównego. Aby uzyskać pełną listę właściwości elementów, zobacz [właściwości elementów na diagramach składników UML](../modeling/properties-of-elements-on-uml-component-diagrams.md).  
  
 ![Elementy na diagramach składników](../modeling/media/uml-compovreading.png "UML_CompOvReading")  
  
|**Kształt**|**Element**|**Opis i właściwości głównego**|  
|---------------|-----------------|-----------------------------------------|  
|1|**Składnik**|Fragment do ponownego wykorzystania funkcji systemu. Składnik udostępnia zużywa zachowanie za pośrednictwem interfejsów i użyć innych składników.<br /><br /> Można ukryć lub pokazać wewnętrznych części składnika za pomocą kontrolki Rozwiń/Zwiń (9).<br /><br /> Składnik jest rodzajem klasy.<br /><br /> -   **Czy wystąpienie utworzono pośrednio**. W przypadku opcji true (domyślnie), składnik istnieje tylko jako artefaktów projektu. W czasie wykonywania istnieje tylko jego części.|  
|2|**Podany Port interfejsu**|Reprezentuje wiadomości w grupie lub wywołuje się, że składnik implementuje i inne składniki lub systemy zewnętrzne służy. Właściwość komponentu, który ma interfejs jak jego typ jest port.|  
|3|**Wymagany Port interfejsu**|Reprezentuje grupę wiadomości lub połączeń, które składnik wysyła do innych składników lub systemów zewnętrznych. Składnik jest przeznaczony do przyłączane do składników, które oferują co najmniej te operacje. Port ma interfejs jako jego typu.|  
|4|**Zależności**|Może służyć do wskazania, że interfejs wymagany, jednego ze składników może być spełnione przez interfejs dostarczany, na innym.<br /><br /> Zależności można również bardziej ogólnie między elementami modelu, aby pokazać, że projekt jednego zależy od projektu z drugiej strony.|  
|5|**Część**|Atrybut składnika, którego typem jest zazwyczaj inny składnik. Element jest używany w wewnętrznego projekcie jej składnika nadrzędnego. Elementy graficzne przedstawiono zagnieżdżone w obrębie składnika nadrzędnego.<br /><br /> Aby utworzyć w ramach istniejącego typu składnika, przeciągnij składnik z Eksploratora modelu UML na składnik właściciela.<br /><br /> Aby utworzyć część nowego typu, kliknij przycisk **składnika** narzędzia, a następnie kliknij składnik właściciela.<br /><br /> Na przykład składnik `Car` składa się z części `engine:CarEngine`, `backLeft:Wheel`, `frontRight:Wheel`i tak dalej.<br /><br /> Więcej niż jedną część mogą mieć tego samego typu i różnych składników mogą mieć części tego samego typu.<br /><br /> -   **Typ**. Typ strony, który jest zdefiniowany w innym miejscu w modelu. Zazwyczaj ten typ jest inny składnik.<br />-   **Liczebność**. Wartość domyślna to 1. Możesz ustawić na **od 0 do 1** do wskazania, że część może mieć wartość **null**, **\*** do wskazania, że część jest kolekcją wystąpień danego typu lub wyrażenie, które może przyjąć zakres numerów.|  
|6|**Zestaw części**|Połączenie między portami wymaganego interfejsu jednej części i porty interfejsem dostarczanym innego. Implementacja zestaw części mogą się różnić od jednego elementu na inny. Połączone elementy muszą mieć ten sam składnik nadrzędny.|  
|7|**Delegowanie**|Łączy portu interfejs jednej części składnika. Wskazuje, czy komunikaty wysyłane do składnika są omówione w części lub wysłane wiadomości wysłanych z część składnika nadrzędnego.|  
|(niewyświetlany)|**Generalizacja**|Wskazuje, że jednego składnika dziedziczy z innego składnika. Części i interfejsy są dziedziczone.|  
|9|Zwiń/Rozwiń kontrolki|Użyj tego, aby ukryć lub pokazać wewnętrznych części składnika.|  
|(niewyświetlany)|**Komentarz**|Aby uzyskać dodatkowe informacje. Komentarz można połączyć dowolną liczbę elementów na diagramie przy użyciu **łącznika** narzędzia.|  
  
## <a name="see-also"></a>Zobacz też  
 [Edytowanie modeli i diagramów UML](../modeling/edit-uml-models-and-diagrams.md)   
 [Diagramy składników UML: wskazówki](../modeling/uml-component-diagrams-guidelines.md)   
 [Weryfikacja systemu w czasie projektowania](../modeling/validate-your-system-during-development.md)   
 [Diagramy przypadków użycia UML: odwołanie](../modeling/uml-use-case-diagrams-reference.md)   
 [Diagramy klas UML: odwołanie](../modeling/uml-class-diagrams-reference.md)   
 [Diagramy aktywności UML: odwołanie](../modeling/uml-activity-diagrams-reference.md)   
 [Diagramy sekwencji UML: informacje](../modeling/uml-sequence-diagrams-reference.md)



