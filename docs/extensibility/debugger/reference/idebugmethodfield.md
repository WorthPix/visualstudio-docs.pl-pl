---
title: IDebugMethodField | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMethodField
helpviewer_keywords:
- IDebugMethodField interface
ms.assetid: a7dc9030-fc98-4cf1-b943-37a4003300b6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5b42f37e0418ec354b522da102adaff3653cfc6a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31118034"
---
# <a name="idebugmethodfield"></a>IDebugMethodField
Ten interfejs opisuje metodę.  
  
## <a name="syntax"></a>Składnia  
  
```  
IDebugMethodField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji  
 Dostawca symbol implementuje ten interfejs dla tego samego obiektu, który implementuje [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) interfejsu. Ten interfejs jest specjalizacji prezentuje metody.  
  
## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania  
 Użyj [QueryInterface](/cpp/atl/queryinterface) uzyskać ten interfejs z [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) interfejsu Jeśli [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) zwraca `FIELD_TYPE_METHOD`. Ponadto metod, [GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md), [GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md), i [EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md), wszystkie zwrot `IDebugMethodField` interfejsu.  
  
## <a name="methods-in-vtable-order"></a>Metody w kolejności Vtable  
 Oprócz metod na [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) i [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) interfejsy, w tym interfejsie implementuje następujących metod:  
  
|Metoda|Opis|  
|------------|-----------------|  
|[EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)|Tworzy moduł wyliczający dla parametrów metody.|  
|[GetThis](../../../extensibility/debugger/reference/idebugmethodfield-getthis.md)|Pobiera wskaźnik "this" obiektu zawierającego metodę.|  
|[EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md)|Tworzy moduł wyliczający dla wszystkich zmiennych lokalnych metody.|  
|[EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)|Tworzy moduł wyliczający dla wybranych zmiennych lokalnych metody.|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugmethodfield-iscustomattributedefined.md)|Określa, czy została zdefiniowana określonego atrybutu niestandardowego.|  
|[EnumStaticLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumstaticlocals.md)|Tworzy moduł wyliczający dla statycznych zmiennych lokalnych metody.|  
|[GetGlobalContainer](../../../extensibility/debugger/reference/idebugmethodfield-getglobalcontainer.md)|Pobiera kontener globalnej metody.|  
|[EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)|Tworzy moduł wyliczający dla typu argumentu wymaganych do wywołania metody.|  
  
## <a name="remarks"></a>Uwagi  
 Metoda może zawierać parametrów, a także zmiennych lokalnych.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Symbol dostawcy interfejsów](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)