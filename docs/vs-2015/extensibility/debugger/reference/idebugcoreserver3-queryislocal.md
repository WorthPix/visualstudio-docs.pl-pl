---
title: IDebugCoreServer3::QueryIsLocal | Dokumentacja firmy Microsoft
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
- IDebugCoreServer3::QueryIsLocal
helpviewer_keywords:
- IDebugCoreServer3::QueryIsLocal
ms.assetid: cca030de-f853-4ed7-b2fb-395f08a6b884
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6cebb27caceca5dd743fbe777092eaee6b2ec966
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49180703"
---
# <a name="idebugcoreserver3queryislocal"></a>IDebugCoreServer3::QueryIsLocal
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Określa, czy serwer lokalny do obiektu wywołującego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT QueryIsLocal(  
   void  
);  
```  
  
```csharp  
int QueryIsLocal();  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Zwraca `S_OK` aby wskazać serwer lokalny. Zwraca `S_FALSE` Jeśli serwer jest uruchomiony z wystąpienia msvsmon.exe, który jest zazwyczaj używany do zdalnego debugowania.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)

