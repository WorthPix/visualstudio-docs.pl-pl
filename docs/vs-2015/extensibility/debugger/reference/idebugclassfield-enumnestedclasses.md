---
title: IDebugClassField::EnumNestedClasses | Dokumentacja firmy Microsoft
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
- IDebugClassField::EnumNestedClasses
helpviewer_keywords:
- IDebugClassField::EnumNestedClasses method
ms.assetid: 2ba5ef0c-395e-4006-9e3c-9b06e1d711d0
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a554c65ca06681aa89fd2583038bf958fc3f51bf
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49281284"
---
# <a name="idebugclassfieldenumnestedclasses"></a>IDebugClassField::EnumNestedClasses
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tworzy moduł wyliczający dla klas zagnieżdżonych w tej klasie.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT EnumNestedClasses(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumNestedClasses(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Zwraca [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) obiekt reprezentujący listę klas zagnieżdżonych. Zwraca wartość null, jeśli nie klas zagnieżdżonych.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca wartość S_OK lub zwraca wartość S_FALSE, jeśli nie klas zagnieżdżonych. W przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Każdy element wyliczenia jest [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) Obiekt opisujący klasę zagnieżdżoną.  
  
 Zagnieżdżona klasa jest klasą zdefiniowane wewnątrz innej klasy. Na przykład:  
  
```  
class RootClass {  
   class NestedClass { }  
};  
```  
  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) wyliczenie będzie zawierał jeden reprezentujący obiekt `NestedClass` klasy.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)

