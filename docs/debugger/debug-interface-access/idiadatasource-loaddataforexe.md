---
title: IDiaDataSource::loadDataForExe | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::loadDataForExe method
ms.assetid: d94a1068-f53f-44b5-b6fb-00dec361a7f2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8ce90f3f46b040662f0b0dc1026dbbed0b5c1166
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
ms.locfileid: "31465168"
---
# <a name="idiadatasourceloaddataforexe"></a>IDiaDataSource::loadDataForExe
Otwiera i przygotowuje skojarzonych z plikiem.exe/.dll danych debugowania.  
  
## <a name="syntax"></a>Składnia  
  
```C++  
HRESULT loadDataForExe (  
   LPCOLESTR executable,  
   LPCOLESTR searchPath,  
   IUnknown* pCallback  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pliku wykonywalnego  
 [in] Ścieżka do pliku .exe lub .dll.  
  
 searchPath  
 [in] Ścieżki alternatywnej do wyszukiwania danych debugowania.  
  
 pCallback  
 [in] `IUnknown` Interfejs dla obiekt, który obsługuje interfejs wywołania zwrotnego debugowania, takich jak [idialoadcallback —](../../debugger/debug-interface-access/idialoadcallback.md), [idialoadcallback2 —](../../debugger/debug-interface-access/idialoadcallback2.md), [idiareadexeatoffsetcallback —](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md), i/lub [idiareadexeatrvacallback —](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) interfejsów.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu. W poniższej tabeli przedstawiono niektóre z kodów błędów możliwe w przypadku tej metody.  
  
|Wartość|Opis|  
|-----------|-----------------|  
|E_PDB_NOT_FOUND|Nie można otworzyć pliku lub plik ma nieprawidłowy format.|  
|E_PDB_FORMAT|Podjęto próbę dostępu do pliku, którego format nie jest przestarzały.|  
|E_PDB_INVALID_SIG|Podpis jest niezgodny.|  
|E_PDB_INVALID_AGE|Niezgodna wiek.|  
|E_INVALIDARG|Nieprawidłowy parametr.|  
|E_UNEXPECTED|Źródło danych zostało już przygotowane.|  
  
## <a name="remarks"></a>Uwagi  
 Nagłówek debugowania pliku.exe/.dll nazwy lokalizacji debugowania skojarzonych danych.  
  
 Ta metoda odczytuje nagłówek debugowania, a następnie wyszukuje i przygotowuje danych debugowania. Postęp wyszukiwania może opcjonalnie zgłaszane i kontrolowane za pośrednictwem wywołania zwrotne. Na przykład [IDiaLoadCallback::NotifyDebugDir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md) jest wywoływane, gdy `IDiaDataSource::loadDataForExe` metody wyszukuje i przetwarza katalog debugowania.  
  
 [Idiareadexeatoffsetcallback —](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md) i [idiareadexeatrvacallback —](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) interfejsy umożliwiają aplikacji klienckiej zapewnić alternatywne metody do odczytywania danych z pliku wykonywalnego pliku, gdy plik Nie można przejść bezpośrednio za pomocą standardowego pliku we/wy.  
  
 Aby załadować plik PDB bez weryfikacji, należy użyć [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) metody.  
  
 Aby sprawdzić poprawność plik PDB przed określone kryteria, należy użyć [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md) metody.  
  
 Aby załadować plik PDB bezpośrednio z pamięci, należy użyć [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md) metody.  
  
## <a name="example"></a>Przykład  
  
```C++  
class MyCallBack: public IDiaLoadCallback  
{  
...  
};  
MyCallBack callback;  
...  
HRESULT hr = pSource->loadDataForExe( L"myprog.exe", L".\debug", (IUnknown*)&callback);  
if (FAILED(hr))  
{  
    // Report error  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Idiadatasource —](../../debugger/debug-interface-access/idiadatasource.md)   
 [Idialoadcallback —](../../debugger/debug-interface-access/idialoadcallback.md)   
 [Idialoadcallback2 —](../../debugger/debug-interface-access/idialoadcallback2.md)   
 [IDiaLoadCallback::NotifyDebugDir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)   
 [Idiareadexeatoffsetcallback —](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [Idiareadexeatrvacallback —](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)   
 [IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)   
 [IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)