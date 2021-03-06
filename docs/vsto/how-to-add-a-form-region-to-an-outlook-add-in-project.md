---
title: 'Porady: dodawanie regionu formularza do projektu dodatek programu Outlook'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.Page1
- VSTO.NewFormRegionWizard.Page3
- VSTO.NewFormRegionWizard.Page2
- VSTO.NewFormRegionWizard.Page0
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], adding
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 875644c10b07eb9c2b338b5a3cdfc827a76a7b34
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2018
ms.locfileid: "34549041"
---
# <a name="how-to-add-a-form-region-to-an-outlook-add-in-project"></a>Porady: dodawanie regionu formularza do projektu dodatek programu Outlook
  Utwórz region formularza, aby rozszerzyć za pomocą standardowych lub niestandardowych formularzy programu Microsoft Office Outlook **nowych regionów formularzy programu Outlook** kreatora. Można utworzyć nowego regionu formularza i projektowanie interfejsu użytkownika w programie Visual Studio lub mogą być importowane regionu formularza, który został zaprojektowany w programie Outlook i Dodaj kod Visual Basic lub C#.  
  
 Jeśli masz regionów formularzy programu Outlook, który został użyty w innym projekcie programu Outlook, może używać go w bieżącym projekcie dodatku narzędzi VSTO programu Outlook przy użyciu **Dodaj istniejący element** okno dialogowe. Aby uzyskać więcej informacji, zobacz [regionów formularzy Outlook utwórz](../vsto/creating-outlook-form-regions.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
### <a name="to-add-a-new-form-region-to-an-outlook-project"></a>Aby dodać nowy regionu formularza do projektu programu Outlook  
  
1.  Otwarcia lub utworzenia projektów dodatku VSTO dla programu Outlook w [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Aby uzyskać więcej informacji, zobacz [porady: tworzenie projektach pakietu Office w Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  W **Eksploratora rozwiązań**, wybierz węzeł projektów dodatku VSTO dla programu Outlook.  
  
3.  Na **projektu** menu, kliknij przycisk **Dodaj nowy element**.  
  
4.  W **Dodaj nowy element** okno dialogowe, wybierz opcję **regionów formularzy programu Outlook**.  
  
5.  Wpisz nazwę do regionu formularza w **nazwa** , a następnie kliknij przycisk **Dodaj**.  
  
     **Regionu formularza NewOutlook** zostanie uruchomiony Kreator.  
  
6.  Na **wybierz jak chcesz utworzyć regionu formularza** wybierz, czy ma być projektowanie regionów formularzy przy przeciągania zarządzane formanty do projektanta wizualnego lub importowanie regionów formularzy, który został zaprojektowany w programie Outlook.  
  
    > [!NOTE]  
    >  Jeśli chcesz zaimportować regionu formularza, który został zaprojektowany w programie Outlook, a następnie należy określić lokalizację magazynu formularzy programu Outlook (*.ofs*) pliku. Nie można dodać zarządzane formanty do regionu formularza, który projekt w programie Outlook; można dodawać tylko kod związany z istniejącego interfejsu użytkownika. Aby uzyskać więcej informacji, zobacz [regionów formularzy Outlook utwórz](../vsto/creating-outlook-form-regions.md).  
  
7.  Na **wybierz typ regionu formularza, którego chcesz utworzyć** , przejrzyj typów regionu formularza i wybierz jedną, a następnie kliknij przycisk **dalej**. Aby uzyskać więcej informacji na temat typów regionu formularza, zobacz [regionów formularzy Outlook utwórz](../vsto/creating-outlook-form-regions.md).  
  
8.  Na **Podaj opis, a następnie wybierz preferencje wyświetlania** strony w **nazwa** wpisz nazwę do regionu formularza. Zastąpienie i typów regionu formularza Zamień wszystkie **tytuł** i **opis** pola są również dostępne.  
  
     Informacje o którym nazwę, tytuł i opis są wyświetlane w programie Outlook podczas wdrażania regionu formularza, zobacz [regionów formularzy Outlook utwórz](../vsto/creating-outlook-form-regions.md).  
  
9. Wybierz co najmniej jeden tryb wyświetlania, w których chcesz regionu formularza i pojawienie się.  
  
     Wszystkie typy regionu formularza może występować w inspektorzy, tworzą trybu (do tworzenia elementów) i w trybie do odczytu (w przypadku wyświetlania elementów). Sąsiadujące, zastąpienia i typów regionu formularza Zamień wszystkie można również wyświetlane w okienku odczytu.  
  
10. Kliknij przycisk **Dalej**.  
  
11. Na **zidentyfikować klasy wiadomości, które spowoduje wyświetlenie tego regionu formularza** , wybierz standardowe klasy wiadomości programu Outlook lub wpisz nazwy co najmniej jedną klasę niestandardowy komunikat, a następnie kliknij przycisk **Zakończ**. Aby uzyskać więcej informacji, zobacz [kojarzenie regionu formularza z klasą wiadomości programu Outlook](../vsto/associating-a-form-region-with-an-outlook-message-class.md).  
  
## <a name="see-also"></a>Zobacz także  
 [Dostęp do regionów formularzy w czasie wykonywania](../vsto/accessing-a-form-region-at-run-time.md)   
 [Rozwiązania programu Outlook](../vsto/outlook-solutions.md)   
 [Tworzenie regionów formularzy programu Outlook](../vsto/creating-outlook-form-regions.md)   
 [Wytyczne dotyczące tworzenia regionów formularzy programu Outlook](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [Wskazówki: Projektowanie regionów formularzy programu Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Wskazówki: Importowanie regionów formularzy zaprojektowanych w programie Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)   
 [Niestandardowe akcje w regionach formularzy programu Outlook](../vsto/custom-actions-in-outlook-form-regions.md)  
  