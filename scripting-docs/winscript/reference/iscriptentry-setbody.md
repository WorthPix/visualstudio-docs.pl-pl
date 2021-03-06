---
title: IScriptEntry::SetBody | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.SetBody
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::SetBody
ms.assetid: 719062e4-98e4-4a7b-946d-6e5dbbcc5225
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 06ee232aa730366e9a23e15cdc45f6734b9ef744
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794896"
---
# <a name="iscriptentrysetbody"></a>IScriptEntry::SetBody
Ustawia tekst, który znajduje się w treści `IScriptEntry` bloku skryptu lub `IScriptScriptlet` skryptlet.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT SetBody(  
   LPCOLESTR          psz  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `psz`  
 [in] Aby uzyskać `IScriptEntry` bloku skryptu `psz` jest tekstem w tagów skryptu.  
  
 Aby uzyskać `IScriptEntry` bloku funkcji `psz` jest treści funkcji.  
  
 Aby uzyskać `IScriptScriptlet` obiektu (pochodzący od `IScriptEntry`), `psz` jest w skrypcie skryptlet.  
  
## <a name="return-value"></a>Wartość zwracana  
 `HRESULT`. Przykładowe dopuszczalne wartości wymieniono w tabeli poniżej.  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`S_OK`|Wykonanie metody powiodło się.|  
  
## <a name="remarks"></a>Uwagi  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejs IScriptEntry](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptEntry::GetBody](../../winscript/reference/iscriptentry-getbody.md)