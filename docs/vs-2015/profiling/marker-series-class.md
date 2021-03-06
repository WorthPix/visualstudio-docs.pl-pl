---
title: marker_series, klasa | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_series
helpviewer_keywords:
- Concurrency::diagnostic::marker_series class
ms.assetid: b8445ed0-c512-4f92-b6b4-3d05c044f939
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5a5791d338b204417d4d765b22a5050f4065faef
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49203862"
---
# <a name="markerseries-class"></a>marker_series — Klasa
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Reprezentuje serial kanał zdarzeń generowanych przez jednego dostawcę.  
  
## <a name="syntax"></a>Składnia  
  
```  
class marker_series;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
### <a name="public-constructors"></a>Konstruktory publiczne  
  
|Nazwa|Opis|  
|----------|-----------------|  
|[Konstruktor marker_series::marker_series](../profiling/marker-series-marker-series-constructor.md)|Inicjuje nowe wystąpienie klasy `marker_series` klasy.|  
|[Destruktor marker_series::~marker_series](../profiling/marker-series-tilde-marker-series-destructor.md)|Niszczy obiekt marker_series i zwalnia wszystkie zasoby przydzielone.|  
  
### <a name="public-methods"></a>Metody publiczne  
  
|Nazwa|Opis|  
|----------|-----------------|  
|[Metoda marker_series::is_enabled](../profiling/marker-series-is-enabled-method.md)|Określa, czy dowolnej sesji ma włączone dostawcy.|  
|[Metoda marker_series::write_alert](../profiling/marker-series-write-alert-method.md)|Zapisuje plik śledzenia Concurrency Visualizer alertu.|  
|[Metoda marker_series::write_flag](../profiling/marker-series-write-flag-method.md)|Zapisuje plik śledzenia Concurrency Visualizer flagę.|  
|[Metoda marker_series::write_message](../profiling/marker-series-write-message-method.md)|Zapisuje komunikat do pliku śledzenia w Wizualizatorze współbieżności.|  
  
## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia  
 `marker_series`  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** cvmarkersobj.h  
  
 **Namespace:** CONCURRENCY::Diagnostic —  
  
## <a name="see-also"></a>Zobacz też  
 [Przestrzeń nazw diagnostic](../profiling/diagnostic-namespace.md)



