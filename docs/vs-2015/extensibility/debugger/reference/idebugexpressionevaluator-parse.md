---
title: IDebugExpressionEvaluator::Parse | Dokumentacja firmy Microsoft
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
- IDebugExpressionEvaluator::Parse
helpviewer_keywords:
- IDebugExpressionEvaluator::Parse method
ms.assetid: e6e31b3a-63a7-4293-bcda-267eb78dffb6
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3531218bcde2303aed749714322111a94ce98f54
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49266750"
---
# <a name="idebugexpressionevaluatorparse"></a>IDebugExpressionEvaluator::Parse
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Ta metoda konwertuje ciąg wyrażenia przeanalizowany wyrażenia.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT Parse(   
   LPCOLESTR                upstrExpression,  
   PARSEFLAGS               dwFlags,  
   UINT                     nRadix,  
   BSTR*                    pbstrError,  
   UINT*                    pichError,  
   IDebugParsedExpression** ppParsedExpression  
);  
```  
  
```csharp  
int Parse(  
   string                     upstrExpression,   
   enum_PARSEFLAGS            dwFlags,   
   uint                       nRadix,   
   out string                 pbstrError,   
   out uint                   pichError,   
   out IDebugParsedExpression ppParsedExpression  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `upstrExpression`  
 [in] Wyrażenie ciąg, który ma być analizowany.  
  
 `dwFlags`  
 [in] Kolekcja [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md) stałe, które określają, jak wyrażenie ma zostać przeanalizowany.  
  
 `nRadix`  
 [in] Podstawy ma być używany do interpretacji wszelkie dane liczbowe.  
  
 `pbstrError`  
 [out] Zwraca błąd jako tekst czytelny dla człowieka.  
  
 `pichError`  
 [out] Zwraca pozycję znaku, Start błędu, w ciągu wyrażenia.  
  
 `ppParsedExpression`  
 [out] Zwraca wyrażenie przeanalizowany w [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) obiektu.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Ta metoda tworzy wyrażenie przeanalizowany, a nie wartość rzeczywistą. Przeanalizowana wyrażenie jest gotowy do można obliczyć, oznacza to, przekonwertować na wartość.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)   
 [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md)

