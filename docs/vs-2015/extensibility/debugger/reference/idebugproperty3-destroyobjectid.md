---
title: IDebugProperty3::DestroyObjectID | Dokumentacja firmy Microsoft
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
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9d60cd58015ef3306c3dbfbc3b9fd9333e077d1e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49274108"
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Niszczy Unikatowy identyfikator skojarzony z tą właściwością wskazujący, że obiekt wywołujący nie jest już dba do identyfikowania tej właściwości, które jednoznacznie ze wszystkich innych właściwości.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT DestroyObjectID(  
   void  
);  
```  
  
```csharp  
int DestroyObjectID();  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Jeśli aparat debugowania nie ma konieczności obsługi unikatowych identyfikatorów dla właściwości (ponieważ jest on już śledzi je jednoznacznie wewnętrznie), a następnie można po prostu zwrócenia `E_NOTIMPL` dla tej metody.  
  
 Unikatowe identyfikatory są tworzone za pomocą wywołania [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) metody, gdy obiekt wywołujący chce upewnić się, ta właściwość jest unikatowo identyfikowana przez inne właściwości.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)

