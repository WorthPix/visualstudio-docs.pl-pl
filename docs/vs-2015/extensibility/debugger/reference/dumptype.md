---
title: DUMPTYPE | Dokumentacja firmy Microsoft
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
- DUMPTYPE
helpviewer_keywords:
- DUMPTYPE enumeration
ms.assetid: ea8160db-8732-4056-a1d7-892ef72da71e
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ffdb44e3c909410f224c2cbbaf945d61bebde0d6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49286042"
---
# <a name="dumptype"></a>DUMPTYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Określa, ile stanu programu (np. uruchamianie wątków, ramek stosu i bieżący adres instrukcji) zrzutu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
enum enum_DUMPTYPE {   
   DUMP_MINIDUMP = 0,  
   DUMP_FULLDUMP = 1  
};  
typedef DWORD DUMPTYPE;  
```  
  
```csharp  
public enum enum_DUMPTYPE {   
   DUMP_MINIDUMP = 0,  
   DUMP_FULLDUMP = 1  
};  
```  
  
## <a name="members"></a>Elementy członkowskie  
 DUMP_MINIDUMP  
 Określa zrzutu małe, compact.  
  
 DUMP_FULLDUMP  
 Określa duża, pełny zrzut.  
  
## <a name="remarks"></a>Uwagi  
 Przekazywany jako argument do [WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md) metody.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Wyliczenia](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md)

