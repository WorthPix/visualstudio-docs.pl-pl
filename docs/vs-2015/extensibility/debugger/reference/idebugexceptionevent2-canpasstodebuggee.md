---
title: IDebugExceptionEvent2::CanPassToDebuggee | Dokumentacja firmy Microsoft
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
- IDebugExceptionEvent2::CanPassToDebuggee
helpviewer_keywords:
- IDebugExceptionEvent2::CanPassToDebuggee
ms.assetid: ae4bbe0a-fbe1-49be-a310-ea64279a434b
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d0e9c4e315554485b31f0ea69977317502111cf2
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49182290"
---
# <a name="idebugexceptionevent2canpasstodebuggee"></a>IDebugExceptionEvent2::CanPassToDebuggee
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Określa, czy aparat debugowania (DE) obsługuje możliwość przekazywania ten wyjątek do debugowanego po wznowieniu działania wykonywania.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT CanPassToDebuggee(  
   void  
);  
```  
  
```csharp  
int CanPassToDebuggee();  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Zwraca albo `S_OK` (wyjątek może być przekazywany do program) lub `S_FALSE` (wyjątek nie mogą być przekazywane).  
  
## <a name="remarks"></a>Uwagi  
 DE musi mieć domyślnej akcji do przekazania do debugowany program. IDE może zostać wyświetlony [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md) zdarzenia i wywołania [Kontynuuj](../../../extensibility/debugger/reference/idebugprocess3-continue.md) metody bez wywoływania `CanPassToDebuggee` metody. W związku z tym DE powinien mieć przypadek domyślny, przekazywania wyjątek, czy nie.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [Continue](../../../extensibility/debugger/reference/idebugprocess3-continue.md)

