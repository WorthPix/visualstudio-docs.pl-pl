---
title: IDebugPropertyCreateEvent2 | Dokumentacja firmy Microsoft
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
- IDebugPropertyCreateEvent2
helpviewer_keywords:
- IDebugPropertyCreateEvent2 interface
ms.assetid: 33b3082b-a42e-488a-a1e4-dadf506f922c
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8efe7a75bdeed6016571a9b6e008eafe7fd0fbb2
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49208939"
---
# <a name="idebugpropertycreateevent2"></a>IDebugPropertyCreateEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Ten interfejs jest wysyłane przez aparat debugowania (DE) w celu Menedżer debugowania sesji (SDM), podczas tworzenia właściwości, który jest skojarzony z określonym dokumentem.  
  
## <a name="syntax"></a>Składnia  
  
```  
IDebugPropertyCreateEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji  
 DE implementuje ten interfejs, aby zgłosić, czy właściwość została utworzona. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) interfejs musi zostać wdrożone na tym samym obiekcie danego interfejsu. Używa SDM [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) dostęp do `IDebugEvent2` interfejsu. Ten interfejs jest implementowany, jeśli DE utworzył właściwość skojarzony ze skryptem, który został załadowany lub utworzone i tego skryptu musi występować w środowisku IDE.  
  
## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania  
 DE tworzy i wysyła tego obiektu zdarzenia do raportu, który utworzył właściwość. Zdarzenia są wysyłane przy użyciu [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkcji wywołania zwrotnego, która jest dostarczana przez SDM, gdy jest on dołączony do debugowanego programu.  
  
## <a name="methods-in-vtable-order"></a>Metody w Vtable kolejności  
 W poniższej tabeli przedstawiono metody `IDebugPropertyCreateEvent2` interfejsu.  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugpropertycreateevent2-getdebugproperty.md)|Pobiera nową właściwość.|  
  
## <a name="remarks"></a>Uwagi  
 Jeśli właściwość jest konkretnym dokumencie lub skrypt skojarzony z nim, DE może wysyłać to zdarzenie SDM, aby można było zaktualizować **dokumenty skryptów** okna o nazwie dokumentu. Wywoła SDM [GetExtendedInfo](../../../extensibility/debugger/reference/idebugproperty2-getextendedinfo.md) z argumentem `guidDocument` można pobrać `VARIANT` zawierający [IUnknown](http://msdn.microsoft.com/library/e6b85472-e54b-4b8c-b19f-4454d6c05a8f) wskaźnika. Wywoła SDM [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) tego wskaźnika można pobrać [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) interfejs, który służy do aktualizowania **dokumenty skryptów** okna.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejsy podstawowe](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)

