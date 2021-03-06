---
title: IDiaSession::findChildren | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findChildren method
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cc9b9aabf920fa33828d86e2f0c3ac96f7e6dbdb
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
ms.locfileid: "31465346"
---
# <a name="idiasessionfindchildren"></a>IDiaSession::findChildren
Pobiera wszystkie elementy podrzędne elementu identyfikator określonego elementu nadrzędnego, zgodnych z typem nazwę i symbol.  
  
## <a name="syntax"></a>Składnia  
  
```C++  
HRESULT findChildren (   
   IDiaSymbol*       parent,  
   SymTagEnum        symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `parent`  
 [in] [Idiasymbol —](../../debugger/debug-interface-access/idiasymbol.md) obiekt reprezentujący element nadrzędny. Jeśli ten symbol nadrzędnego jest funkcją, modułu lub bloku, a następnie leksykalne elementy podrzędne są zwracane w `ppResult`. Jeśli nadrzędny symbol jest typem, klasa elementy podrzędne są zwracane. Jeśli ten parametr ma `NULL`, następnie `symtag` musi mieć ustawioną `SymTagExe` lub `SymTagNull`, która zwraca zakresu globalnego (pliku .exe).  
  
 `symtag`  
 [in] Określa symbol znacznika elementów podrzędnych, które mają zostać pobrane. Wartości są pobierane z [symtagenum — wyliczenie](../../debugger/debug-interface-access/symtagenum.md) wyliczenia. Ustaw `SymTagNull` można pobrać wszystkie elementy podrzędne.  
  
 `name`  
 [in] Określa nazwę elementu podrzędnego, które mają zostać pobrane. Ustaw `NULL` dla wszystkich elementów podrzędnych do pobrania.  
  
 `compareFlags`  
 [in] Określa opcje porównania stosowane do dopasowania nazwy. Wartości z [namesearchoptions — wyliczenie](../../debugger/debug-interface-access/namesearchoptions.md) wyliczenie można samodzielnie lub w połączeniu.  
  
 `ppResult`  
 [out] Zwraca [idiaenumsymbols —](../../debugger/debug-interface-access/idiaenumsymbols.md) pobrać obiekt, który zawiera listę symbolami podrzędnymi.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak można znaleźć zmiennych lokalnych funkcji `pFunc` tę nazwę dopasowania `szVarName`.  
  
```C++  
IDiaEnumSymbols* pEnum;  
pSession->findChildren( pFunc, SymTagData, szVarName, nsCaseSensitive, &pEnum );  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Omówienie](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [Idiaenumsymbols —](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession —](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol —](../../debugger/debug-interface-access/idiasymbol.md)   
 [Namesearchoptions — wyliczenie](../../debugger/debug-interface-access/namesearchoptions.md)   
 [Symtagenum — wyliczenie](../../debugger/debug-interface-access/symtagenum.md)