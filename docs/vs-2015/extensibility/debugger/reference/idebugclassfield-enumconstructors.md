---
title: IDebugClassField::EnumConstructors | Dokumentacja firmy Microsoft
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
- IDebugClassField::EnumConstructors
helpviewer_keywords:
- IDebugClassField::EnumConstructors method
ms.assetid: 66a250b2-75a0-45aa-8d58-40f91cc4bf7b
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 526e0b129e07a7c52f7f4215e1f61d1c4f306061
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49276955"
---
# <a name="idebugclassfieldenumconstructors"></a>IDebugClassField::EnumConstructors
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tworzy moduł wyliczający dla konstruktorów dla tej klasy.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT EnumConstructors(   
   CONSTRUCTOR_ENUM   cMatch,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumConstructors(  
   CONSTRUCTOR_ENUM     cMatch,   
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cMatch`  
 [in] Wartość z zakresu od [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md) wyliczenie, który określa typ konstruktorów do wyliczenia.  
  
 `ppEnum`  
 [out] Zwraca [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) obiekt reprezentujący listę konstruktorów. Zwraca wartość null, jeśli nie ma żadnych konstruktorów.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca wartość S_OK lub zwraca wartość S_FALSE, jeśli nie ma żadnych konstruktorów. W przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Każdy element wyliczenia jest [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) Obiekt opisujący metodę konstruktora.  
  
 Lista konstruktory zwykle nie ma konstruktory domyślne, dostarczone przez kompilator.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md)

