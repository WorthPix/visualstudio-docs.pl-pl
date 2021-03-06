---
title: IDebugProgramNode2::Attach_V7 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramNode2::Attach
helpviewer_keywords:
- IDebugProgramNode2::Attach_V7
- IDebugProgramNode2::Attach
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e77acd4091abd7da5c9d302fb4c4dd6eb66af379
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31122993"
---
# <a name="idebugprogramnode2attachv7"></a>IDebugProgramNode2::Attach_V7

> [!Note]
> PRZESTARZAŁE. NIE UŻYWAJ.

## <a name="syntax"></a>Składnia

```cpp
HRESULT Attach_V7 (
   IDebugProgram2*       pMDMProgram,
   IDebugEventCallback2* pCallback,
   DWORD                 dwReason
);
```

```csharp
int Attach_V7 (
   IDebugProgram2       pMDMProgram,
   IDebugEventCallback2 pCallback,
   uint                 dwReason
);
```

#### <a name="parameters"></a>Parametry

`pMDMProgram` [in] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) interfejs, który reprezentuje program można dołączyć do.

 `pCallback` [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) interfejs służący do wysyłania zdarzeń debugowania do SDM.

 `dwReason` [in] Wartość z zakresu od [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) wyliczenie określający przyczynę dołączania.

## <a name="return-value"></a>Wartość zwracana

Implementacja zawsze powinna zwrócić `E_NOTIMPL`.

## <a name="remarks"></a>Uwagi

> [!WARNING]
> Począwszy od programu Visual Studio 2005, ta metoda nie jest już używany i powinien zawsze zwracają `E_NOTIMPL`. Zobacz [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md) interfejs dla o innym podejściu, jeśli węzeł program musi wskazywać, nie można dołączyć do lub węzeł program po prostu ustawia program `GUID`. W przeciwnym razie zaimplementować [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) metody.

## <a name="prior-to-visual-studio-2005"></a>Przed programu Visual Studio 2005

Ta metoda musi być zaimplementowany tylko wtedy, gdy DE działa w przestrzeni adresowej debugowanego programu. W przeciwnym razie ta metoda powinna zwrócić `S_FALSE`.

Gdy ta metoda jest wywoływana, DE musi wysłać [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md) obiektu zdarzenia, jeśli go nie ma już wysłane dla tego wystąpienia [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) interfejsu, jak również [ IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) i [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md) obiektów zdarzeń. [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md) zdarzenia obiektu jest następnie wysyłana, jeśli `dwReason` parametr jest `ATTACH_REASON_LAUNCH`.

Niemcy należy wywołać [GetProgramId](../../../extensibility/debugger/reference/idebugprogram2-getprogramid.md) metoda [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) dostarczony przez obiekt [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) zdarzeń obiektu i identyfikator GUID tego programu muszą zostać zapisane w danych wystąpienia `IDebugProgram2` implementowane przez DE obiektu.

## <a name="see-also"></a>Zobacz też

[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)  
[IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)  
[Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)  
[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)  
[IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)  
[IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)  
[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
[IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)  
[IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)  
[ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md)