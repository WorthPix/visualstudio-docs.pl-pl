---
title: DISASSEMBLY_STREAM_SCOPE | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DISASSEMBLY_STREAM_SCOPE
helpviewer_keywords:
- DISASSEMBLY_STREAM_SCOPE enumeration
ms.assetid: 43e2b364-cbbe-4755-a7e6-a03f3054c965
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a0c72d0f14da9840c0a77d5ae88cb0acb5b54cba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31102070"
---
# <a name="disassemblystreamscope"></a>DISASSEMBLY_STREAM_SCOPE
Określa zakres strumienia dezasemblacji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
typedef DWORD DISASSEMBLY_STREAM_SCOPE;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
```  
  
## <a name="members"></a>Elementy członkowskie  
 DSS_HUGE  
 Określa, że dezasemblowanie kontekst kodu powoduje wygenerowanie moc niż zwykle chce pobierać w pojedynczym wywołaniu klienta.  
  
 DSS_FUNCTION  
 Określa, że funkcja zawarty w kontekście kod powinien dezasemblowania. Określa, że strumienia dezasemblacji reprezentuje funkcję, gdy zwracany przez [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) metody.  
  
 DSS_MODULE  
 Zwracanie przez `IDebugDisassemblyStream2::GetScope` metody, określa, czy strumień dezasemblacji reprezentuje modułu.  
  
 DSS_ALL  
 Określa dezasemblacji dla całej przestrzeni.  
  
## <a name="remarks"></a>Uwagi  
 Przekazany jako argument [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) — metoda i zwrócony przez [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) metody.  
  
 Te wartości mogą być łączone z bitowego `OR`.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Wyliczenia](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)