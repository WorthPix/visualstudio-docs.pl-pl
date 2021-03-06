---
title: 'Porady: Instalowanie wizualizatora | Dokumentacja firmy Microsoft'
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
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5539b17ee4d10f603f1adfe2ce7e459332181cf
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49250227"
---
# <a name="how-to-install-a-visualizer"></a>Porady: instalacja programu Visualizer
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Po utworzeniu wizualizatora, należy zainstalować wizualizatora tak, że będzie on dostępny w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Instalowanie wizualizatora jest prostym procesem.  
  
> [!NOTE]
>  W **Store** aplikacji, tylko standardowy tekst, HTML, XML i JSON wizualizatory są obsługiwane. Wizualizatory niestandardowe (utworzone przez użytkownika) nie są obsługiwane.  
  
### <a name="to-install-a-visualizer"></a>Aby instalacja programu visualizer  
  
1.  Znajdź bibliotekę DLL, która zawiera visualizer, który został wcześniej utworzony.  
  
2.  Kopiuj bibliotekę DLL do jednej z następujących lokalizacji:  
  
    -   *VisualStudioInstallPath* `\Common7\Packages\Debugger\Visualizers`  
  
    -   `My Documents\` *VisualStudioVersion* `\Visualizers`  
  
3.  Jeśli chcesz użyć zarządzany Wizualizator dla zdalnego debugowania, należy skopiować bibliotekę DLL do tej samej ścieżki na komputerze zdalnym.  
  
4.  Uruchom ponownie sesję debugowania.  
  
## <a name="see-also"></a>Zobacz też  
 [Tworzenie niestandardowych Wizualizatorów](../debugger/create-custom-visualizers-of-data.md)   
 [Instrukcje: pisanie wizualizatora](../debugger/how-to-write-a-visualizer.md)



