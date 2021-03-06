---
title: IDebugCoreServer3::CreateInstanceInServer | Dokumentacja firmy Microsoft
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
- IDebugCoreServer3::CreateInstanceInServer
helpviewer_keywords:
- IDebugCoreServer3::CreateInstanceInServer
ms.assetid: 76f36bae-f6ab-413c-a8a9-8808bfeba05b
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8f61661759f916d6d9ac82a1c17aaff11fb8242a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49284807"
---
# <a name="idebugcoreserver3createinstanceinserver"></a>IDebugCoreServer3::CreateInstanceInServer
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tworzy wystąpienie aparatu debugowania na serwerze.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT CreateInstanceInServer(  
   LPCWSTR  szDll,  
   WORD     wLangId,  
   REFCLSID clsidObject,  
   REFIID   riid,  
   void**   ppvObject  
);  
```  
  
```csharp  
int CreateInstanceInServer(  
   string     szDll,   
   ushort     wLangID,   
   ref Guid   clsidObject,   
   ref Guid   riid,   
   out IntPtr ppvObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `szDll`  
 [in] Ścieżka do biblioteki dll, która implementuje CLSID określone w `clsidObject` parametru. Jeśli jest to `NULL`, następnie modelu COM `CoCreateInstance` funkcja jest wywoływana.  
  
 `wLangId`  
 [in] Ustawienia regionalne aparatu debugowania. Może to być 0, jeśli [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md) nie powinna być wywoływana metoda.  
  
 `clsidObject`  
 [in] Identyfikator CLSID aparat debugowania do utworzenia.  
  
 `riid`  
 [in] Identyfikator interfejsu określonego interfejsu, aby pobrać z obiektu klasy.  
  
 `ppvObject`  
 [out] `IUnknown` interfejsu z wystąpieniami obiektu. Rzutowanie lub kierować się ten obiekt do żądanego interfejsu.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)

