---
title: Funkcja SccEnumChangedFiles | Dokumentacja firmy Microsoft
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
- SccEnumChangedFiles
helpviewer_keywords:
- SccEnumChangedFiles function
ms.assetid: 76cac510-107b-4c1a-ba60-9c39b6db2e71
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e4bc5595b5421e0be0139598464e70c6af52df80
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49294479"
---
# <a name="sccenumchangedfiles-function"></a>SccEnumChangedFiles, funkcja
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Podana lista plików lokalnych, ta funkcja sprawdza pliki, które różnią się od odpowiedniej wersji w bazie danych kontroli kodu źródłowego.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
SCCRTN SccEnumChangedFiles(  
   LPVOID  pContext,  
   HWND    hWnd,  
   LONG    cFiles,  
   LPCSTR* lpFileNames,  
   LONG*   plIsFileDifferent  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [in] Wskaźnik kontekście wtyczki kontroli źródła.  
  
 hWnd  
 [in] Uchwyt okna środowiska IDE, które wtyczka do kontroli źródła można użyć jako element nadrzędny dla wszystkie okna dialogowe, które zawiera.  
  
 cFiles  
 [in] Liczby nazw plików określonych w `lpFileNames` tablicy. Również określa rozmiar `plIsFileDifferent` tablicy.  
  
 lpFileNames  
 [in] Tablica nazw plik lokalny do sprawdzenia.  
  
 plIsFileDifferent  
 [out w] Tablica wartości wskazujący stan różnica każdego pliku (Tablica musi mieć co najmniej `cFiles` wpisy). Wartość różną od zera oznacza, że plik jest inny.  
  
## <a name="return-value"></a>Wartość zwracana  
 Implementacja wtyczki kontroli źródła tej funkcji powinien zwrócić jedną z następujących wartości:  
  
|Wartość|Opis|  
|-----------|-----------------|  
|SCC_OK|Operacja została ukończona pomyślnie.|  
|SCC_UNSPECIFIEDERROR|Błąd ogólny.|  
  
## <a name="see-also"></a>Zobacz też  
 [Funkcje interfejsu API wtyczki kontroli źródła ](../extensibility/source-control-plug-in-api-functions.md)

