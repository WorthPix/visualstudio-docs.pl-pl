---
title: BP_STATE | Dokumentacja firmy Microsoft
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
- BP_STATE
helpviewer_keywords:
- BP_STATE enumeration
ms.assetid: 08aa6a3f-3e5f-4c83-8eca-7b7b5f8e208d
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8973bf18fdcf81d174216568b753cdd805f483bb
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49288720"
---
# <a name="bpstate"></a>BP_STATE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Określa istnienie powiązany punkt przerwania i określa, czy jest włączony.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
enum enum_BP_STATE {   
   BPS_NONE     = 0x0000,  
   BPS_DELETED  = 0x0001,  
   BPS_DISABLED = 0x0002,  
   BPS_ENABLED  = 0x0003  
};  
typedef DWORD BP_STATE;  
```  
  
```csharp  
public enum enum_BP_STATE {   
   BPS_NONE     = 0x0000,  
   BPS_DELETED  = 0x0001,  
   BPS_DISABLED = 0x0002,  
   BPS_ENABLED  = 0x0003  
};  
```  
  
## <a name="members"></a>Elementy członkowskie  
 BPS_NONE  
 Określa, czy istnieje nie punktu przerwania.  
  
 BPS_DELETED  
 Określa, że punkt przerwania został usunięty.  
  
 BPS_DISABLED  
 Określa, że punkt przerwania jest wyłączona.  
  
 BPS_ENABLED  
 Określa, że punkt przerwania jest włączony.  
  
## <a name="remarks"></a>Uwagi  
 Zwrócone w wyniku [GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md) metody.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Wyliczenia](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetState](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)

