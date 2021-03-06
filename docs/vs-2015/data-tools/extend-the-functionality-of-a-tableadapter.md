---
title: Rozszerzanie funkcjonalności TableAdapter | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- data [Visual Studio], extending TableAdapters
- TableAdapters, adding functionality
ms.assetid: 418249c8-c7f3-47ef-a94c-744cb6fe6aaf
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 79710dca958bbc895e5366e4ab316f1a1e4fa64c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49234473"
---
# <a name="extend-the-functionality-of-a-tableadapter"></a>Rozszerzanie funkcjonalności adaptera TableAdapter
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Funkcjonalności TableAdapter można rozszerzyć, dodając kod do pliku częściowej klasy TableAdapter.  
  
 Wygenerowania kodu, który definiuje TableAdapter gdy zmiany zostaną wprowadzone do elementu TableAdapter w **Projektanta obiektów Dataset**, lub gdy modyfikuje przez Kreatora konfiguracji TableAdapter. Aby zapobiec usunięciu podczas ponownego generowania TableAdapter w kodzie, należy dodać kod do pliku częściowej klasy TableAdapter.  
  
 Klasy częściowe umożliwiają kod dla określonej klasy do podzielone między wiele plików fizycznych. Aby uzyskać więcej informacji, zobacz [częściowe](http://msdn.microsoft.com/library/7adaef80-f435-46e1-970a-269fff63b448) lub [partial (typ)](http://msdn.microsoft.com/library/27320743-a22e-4c7b-b0b3-53afe3607334).  
  
## <a name="locate-tableadapters-in-code"></a>Znajdź TableAdapters w kodzie  
 Gdy TableAdapters są skonstruowane z **Projektanta obiektów Dataset**, klasy TableAdapter, które są generowane, nie są klas zagnieżdżonych <xref:System.Data.DataSet>. TableAdapters znajdują się w przestrzeni nazw na podstawie nazwy dataset skojarzony obiekt TableAdapter. Na przykład, jeśli aplikacja zawiera zestaw danych o nazwie `HRDataSet`, elementów TableAdapter znajduje się w `HRDataSetTableAdapters` przestrzeni nazw. (Konwencji nazewnictwa tym wzorcem: *DatasetName* + `TableAdapters`).  
  
 W poniższym przykładzie założono TableAdapter o nazwie `CustomersTableAdapter`znajduje się w projekcie z `NorthwindDataSet`.  
  
#### <a name="to-create-a-partial-class-for-a-tableadapter"></a>Aby utworzyć klasę częściową dla adaptera TableAdapter  
  
1.  Dodaj nową klasę do projektu, przechodząc do **projektu** menu i wybierając polecenie**Dodaj klasę**.  
  
2.  Nazwa klasy `CustomersTableAdapterExtended`.  
  
3.  Wybierz**Dodaj**.  
  
4.  Zastąp kod poprawną przestrzeń nazw i nazwę klasy częściowej projektu w następujący sposób:  
  
     [!code-csharp[VbRaddataTableAdapters#2](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataTableAdapters/CS/CustomersTableAdapterExtended.cs#2)]
     [!code-vb[VbRaddataTableAdapters#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataTableAdapters/VB/CustomersTableAdapterExtended.vb#2)]  
  
## <a name="see-also"></a>Zobacz też  
 [Wypełnianie zestawów danych za pomocą adapterów TableAdapter](../data-tools/fill-datasets-by-using-tableadapters.md)

