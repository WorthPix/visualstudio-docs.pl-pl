---
title: IDebugClassField::EnumBaseClasses | Dokumentacja firmy Microsoft
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
- IDebugClassField::EnumBaseClasses
helpviewer_keywords:
- IDebugClassField::EnumBaseClasses method
ms.assetid: 78749674-ef75-46d3-a1f4-ff33afd90e32
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 85507cbecc0ef2739f7cf78f8645c3ec9735172f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49182120"
---
# <a name="idebugclassfieldenumbaseclasses"></a>IDebugClassField::EnumBaseClasses
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tworzy moduł wyliczający dla klasy bazowe tej klasy.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT EnumBaseClasses(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumBaseClasses(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Zwraca [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) obiekt reprezentujący listę klas bazowych. Zwraca wartość null, jeśli nie mają klas bazowych.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca wartość S_OK, funkcja zwraca S_SH_NO_BASE_CLASSES, jeśli nie mają klas bazowych (i `ppEnum` parametr jest ustawiony na wartość null); w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Klasy bazowe w obiekcie moduł wyliczający są określone w kolejności od najbardziej bezpośredni (lub najbardziej pochodnej) klasy bazowej do klasy bazowej najbardziej zdalnego. Na przykład biorąc klasy C++:  
  
```  
class Root { }  
class Level1 : Root { }  
class Level2 : Level1 { }  
class MyClass : Level2 { }  
```  
  
 Wyliczanie zwróci bazowe klasy w kolejności `Level2`, `Level1`, `Root`.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)

