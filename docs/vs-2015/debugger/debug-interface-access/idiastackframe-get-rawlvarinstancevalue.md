---
title: Idiastackframe::get_rawlvarinstancevalue — | Dokumentacja firmy Microsoft
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
- C++
helpviewer_keywords:
- IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 440a780ccd92a6f8f46f74c462e4adfc591c97ce
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49175516"
---
# <a name="idiastackframegetrawlvarinstancevalue"></a>IDiaStackFrame::get_rawLVarInstanceValue
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ta metoda pobiera wartość określonej zmiennej lokalnej, jako bajtów raw.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT get_rawLVarInstanceValue(  
   IDiaLVarInstance* pInstance,  
   DWORD             cbDataMax,  
   DWORD*            pcbData,  
   BYTE*             pbData  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pInstance`  
 [in] `IDiaLVarInstance` Obiekt reprezentujący wystąpienie zmiennej lokalnej, aby uzyskać wartość.  
  
 `cbDataMax`  
 [in] Maksymalna liczba bajtów w buforze wskazywany przez `pbData`. Może to być maksymalnie 8 bajtów (`sizeof(ULONGLONG)`).  
  
 `pcbData`  
 [out] Zwraca wartość rzeczywista liczba bajtów przechowywanych w buforze.  
  
 `pbData`  
 [out] Bufor w celu wprowadzenia danych. Nie może to być `NULL`.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="see-also"></a>Zobacz też  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)



