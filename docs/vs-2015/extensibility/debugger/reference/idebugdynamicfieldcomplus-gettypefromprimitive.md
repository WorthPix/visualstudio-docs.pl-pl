---
title: IDebugDynamicFieldCOMPlus::GetTypeFromPrimitive | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugDynamicFieldCOMPlus::GetTypeFromPrimitive
- GetTypeFromPrimitive
ms.assetid: d7f51e2a-1b72-489c-b7b6-4af7b7e4d663
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 39f8ce700b48579e885b1e8c9c22899efb2c8627
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49223395"
---
# <a name="idebugdynamicfieldcomplusgettypefromprimitive"></a>IDebugDynamicFieldCOMPlus::GetTypeFromPrimitive
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Pobiera typ danego typu pierwotnego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT GetTypeFromPrimitive(  
   DWORD         dwCorElementType,  
   IDebugField** ppType  
);  
```  
  
```csharp  
int GetTypeFromPrimitive(  
   uint            dwCorElementType,  
   out IDebugField ppType  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwCorElementType`  
 [in] Wartość z [corelementtype — wyliczenie](/dotnet/framework/unmanaged-api/metadata/corelementtype-enumeration) reprezentujący typu pierwotnego.  
  
 `ppType`  
 [out] Zwraca [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) reprezentujący typ.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugDynamicFieldCOMPlus](../../../extensibility/debugger/reference/idebugdynamicfieldcomplus.md)

