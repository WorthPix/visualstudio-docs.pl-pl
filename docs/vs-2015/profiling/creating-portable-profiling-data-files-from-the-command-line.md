---
title: Tworzenie przenośna profilowania pliki danych z poziomu wiersza polecenia | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8f2a2979fdc836f0204dec580d49e86ae235d5c1
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49254699"
---
# <a name="creating-portable-profiling-data-files-from-the-command-line"></a>Tworzenie przenośnych plików danych profilowania z wiersza polecenia
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Aby ułatwić udostępnianie danych ułatwia profilowania, można użyć [VSPerfReport](../profiling/vsperfreport.md) narzędzie wiersza polecenia, aby osadzić symbole dla profilowania do pliku Vsp.  
  
 Można również utworzyć wstępnie przeanalizowany profilowania plik danych (.vsps), który jest mniejszy i jest szybsze ładowanie w środowisku IDE.  
  
> [!NOTE]
>  Upewnij się, że pliki symboli (.pdb) są dostępne dla **VSPerfReport**. Aby uzyskać więcej informacji, zobacz [porady: Określanie lokalizacji plików symboli z wiersza polecenia](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md).  
>   
>  Aby uzyskać informacje o ścieżce do **VSReport**, zobacz [Określanie ścieżki do narzędzi wiersza polecenia](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Nie można filtrować dane profilowania w pliku .vsps.  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>Aby osadzić symbole dla profilowania w pliku danych (Vsp) profilowania  
  
-   W oknie wiersza polecenia wpisz następujące polecenie:  
  
     \<Ścieżka >**VSPerfReport \<** pliku VSP > **packsymbols**  
  
     Domyślnie plik .vsps nosi nazwę z podstawowej nazwy pliku Vsp. Należy określić nazwę alternatywną, za pomocą **dane wyjściowe** opcji.  
  
### <a name="to-create-a-summary-profiling-data-file"></a>Aby utworzyć plik danych profilowania podsumowania  
  
-   W oknie wiersza polecenia wpisz następujące polecenie:  
  
     \<Ścieżka >**VSPerfReport \<** pliku VSP > **/summaryfile** [**/Output:**\<nazwa pliku >]  
  
     Domyślnie plik .vsps nosi nazwę z podstawowej nazwy pliku Vsp. Należy określić nazwę alternatywną, za pomocą **dane wyjściowe** opcji.



