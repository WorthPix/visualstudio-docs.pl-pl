---
title: IEnumDebugModules2::Next | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEnumDebugModules2::Next
helpviewer_keywords:
- IEnumDebugModules2::Next
ms.assetid: 46b7ccad-b07b-4ec0-b3ce-13981ffab7e8
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: de3e9d029a8d51f61c83ef81444116af83e64e8e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49282220"
---
# <a name="ienumdebugmodules2next"></a>IEnumDebugModules2::Next
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Zwraca następny zestaw elementów z wyliczenia.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT Next(  
   ULONG           celt,  
   IDebugModule2** rgelt,  
   ULONG*          pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint            celt,  
   IDebugModule2[] rgelt,  
   ref uint        pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [in] Liczba elementów do pobrania. Również określa maksymalny rozmiar `rgelt` tablicy.  
  
 `rgelt`  
 [out w] Tablica [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) elementami do wypełnienia.  
  
 `pceltFetched`  
 [out] Zwraca liczbę elementów, w rzeczywistości są zwracane w `rgelt`.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`. Zwraca `S_FALSE` Jeśli mniej niż żądana liczba elementów, które mogą być zwracane; w przeciwnym razie zwraca kod błędu.  
  
## <a name="see-also"></a>Zobacz też  
 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)

