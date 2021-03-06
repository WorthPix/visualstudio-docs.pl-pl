---
title: Funkcja SccRunScc | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccRunScc
helpviewer_keywords:
- SccRunScc function
ms.assetid: bbe7c931-b17a-4779-9cf6-59e5f9f0c172
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 322ebe148144260106fb895273b66e1b9f5696f8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31138268"
---
# <a name="sccrunscc-function"></a>Funkcja SccRunScc
Ta funkcja wywołuje narzędzie do administrowania kontroli źródła.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
SCCRTN SccRunScc(  
   LPVOID  pvContext,  
   HWND    hWnd,  
   LONG    nFiles,  
   LPCSTR* lpFileNames  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [in] Struktura kontekstu wtyczkę kontroli źródła.  
  
 Właściwość hWnd  
 [in] Dojście do okna IDE, które wtyczka do kontroli źródła można używać jako elementu nadrzędnego wszystkie okna dialogowe, które zawiera.  
  
 To  
 [in] Liczba plików określonych w `lpFileNames` tablicy.  
  
 lpFileNames  
 [in] Tablica nazw wybranego pliku.  
  
## <a name="return-value"></a>Wartość zwracana  
 Implementacja wtyczkę kontroli źródła tej funkcji może przywrócić jedną z następujących wartości:  
  
|Wartość|Opis|  
|-----------|-----------------|  
|SCC_OK|Narzędzie do administrowania kontroli źródła został pomyślnie wywołany.|  
|SCC_I_OPERATIONCANCELED|Operacja została anulowana.|  
|SCC_E_INITIALIZEFAILED|Nie można zainicjować systemu kontroli źródła.|  
|SCC_E_ACCESSFAILURE|Wystąpił problem podczas uzyskiwania dostępu do systemu kontroli źródła, prawdopodobnie z powodu problemów z siecią lub rywalizacji.|  
|SCC_E_CONNECTIONFAILURE|Nie można połączyć z systemu kontroli źródła.|  
|SCC_E_FILENOTCONTROLLED|Wybrany plik nie jest pod kontrolą źródła.|  
|SCC_E_NONSPECIFICERROR|Nieokreślony błąd.|  
  
## <a name="remarks"></a>Uwagi  
 Ta funkcja umożliwia wywołującego dostęp pełny zakres funkcji systemu kontroli źródła przy użyciu narzędzia do administrowania zewnętrznych. Jeśli system kontroli źródła nie ma interfejsu użytkownika, wtyczkę kontroli źródła może implementować interfejs do wykonywania zadań administracyjnych niezbędne.  
  
 Ta funkcja jest wywoływana z liczbą i tablicę nazw plików dla aktualnie wybranych plików. Jeśli narzędzie administracyjne obsługuje tę funkcję, lista plików może służyć do wstępnego wyboru plików w interfejsie Administracja; w przeciwnym razie listy można zignorować.  
  
 Ta funkcja jest zwykle wywoływane, gdy użytkownik wybierze **uruchamianie \<serwera kontroli źródła >** z **pliku** -> **kontroli źródła** menu. To **uruchamianie** opcji menu można zawsze wyłączona lub nawet ukryty przez ustawienie wpisu rejestru. Zobacz [porady: Instalowanie dodatku Plug-in kontroli źródła](../extensibility/internals/how-to-install-a-source-control-plug-in.md) szczegółowe informacje. Ta funkcja jest wywoływana tylko wtedy, gdy [SccInitialize](../extensibility/sccinitialize-function.md) zwraca `SCC_CAP_RUNSCC` bit możliwości (zobacz [flagi możliwości](../extensibility/capability-flags.md) Aby uzyskać więcej informacji na ten temat oraz innych możliwości usługi bits).  
  
## <a name="see-also"></a>Zobacz też  
 [Funkcje API wtyczkę kontroli źródła](../extensibility/source-control-plug-in-api-functions.md)   
 [Porady: Instalowanie dodatku Plug-in kontroli źródła](../extensibility/internals/how-to-install-a-source-control-plug-in.md)   
 [Flagi możliwości](../extensibility/capability-flags.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)