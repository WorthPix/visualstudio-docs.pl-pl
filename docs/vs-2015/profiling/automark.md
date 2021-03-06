---
title: AutoMark | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4de965e-0364-4f78-9936-1f509e85df74
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8ee6e4beafb21ed7f7695c88fceb8516d5677cdb
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49259265"
---
# <a name="automark"></a>AutoMark
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**AutoMark** opcja określa liczbę milisekund między zbierania zdarzeń liczników wydajności oprogramowania Windows. Liczniki wydajności Windows są określone w **WinCounter** opcji.  
  
 Tylko jeden **AutoMark** opcja może być określona w wierszu polecenia. Należy pamiętać, że **WinCounter** interwał próbkowania określony przez **AutoMark** jest niezależna od interwału próbkowania głównego.  
  
## <a name="syntax"></a>Składnia  
  
```  
VSPerfCmd.exe /Start:Method /WinCounter:Path /AutoMark:Milliseconds  
```  
  
#### <a name="parameters"></a>Parametry  
 `Milliseconds`  
 Określa liczbę milisekund między kolekcji zdarzeń licznika wydajności Windows.  
  
## <a name="required-options"></a>Wymagane opcje  
 **WinCounter:** `Path`  
 Określa Windows licznika wydajności do zbierania. Korzystając z metody instrumentacji, można określić wiele liczników Windows. Korzystając z metody pobierania próbek, można określić tylko jeden licznik oprogramowania. **WinCounter** opcja musi być określona w wierszu polecenia, który zawiera **Start** opcji.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie dla dwóch liczników wydajności Windows ustawiono interwał próbkowania 1000 milisekund.  
  
```  
VSPerfCmd.exe /Start:Trace /Output:TestApp.exe.vsp /WinCounter:"\Process(*)\% Processor Time" /WinCounter:"\ASP.NET\Pages/sec" /AutoMark:1000  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Narzędzia VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilowanie aplikacji autonomicznych](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilowanie aplikacji sieci Web platformy ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Usługi profilowania](../profiling/command-line-profiling-of-services.md)



