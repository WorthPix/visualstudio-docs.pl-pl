---
title: IDebugArrayObject::GetElements | Dokumentacja firmy Microsoft
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
- IDebugArrayObject::GetElements
helpviewer_keywords:
- IDebugArrayObject::GetElements method
ms.assetid: f6a6262f-5183-46ce-8a45-33ef46088b98
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9d838b938f4dbe3bb4e703c847b65b25fe3d83dc
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49278255"
---
# <a name="idebugarrayobjectgetelements"></a>IDebugArrayObject::GetElements
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Pobiera moduł wyliczający wszystkie elementy tablicy.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT GetElements(   
   IEnumDebugObjects** ppEnum  
);  
```  
  
```csharp  
int GetElements(  
   out IEnumDebugObjects ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Zwraca [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md) obiekt, który umożliwia wyliczania przez wszystkie elementy.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca wartość S_OK; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Alternatywnie użyj [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) i [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md) metody służące do iterowania po elementach.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)

