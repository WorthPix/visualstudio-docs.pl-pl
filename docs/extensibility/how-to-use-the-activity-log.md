---
title: 'Porady: Korzystanie z dziennika aktywności | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, debugging
- VSPackages, troubleshooting
ms.assetid: bb3d3322-0e5e-4dd5-b93a-24d5fbcd2ffd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3b5647a62064857bca6a6352a14fe56eff4386f9
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497999"
---
# <a name="how-to-use-the-activity-log"></a>Porady: Korzystanie z dziennika aktywności
Pakietów VSPackage może zapisywać komunikaty w dzienniku aktywności. Ta funkcja jest szczególnie przydatna podczas debugowania pakietów VSPackage w środowisku handlu detalicznego.  
  
> [!TIP]
>  Dziennik aktywności jest zawsze włączone. Visual Studio przechowuje stopniowe buforu 100 ostatnich operacji wpisy, a także 10 pierwszych zapisów, które udostępniają informacje o konfiguracji ogólnej.  
  
## <a name="to-write-an-entry-to-the-activity-log"></a>Aby zapisać wpis w dzienniku aktywności  
  
1.  Wstaw ten kod w <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metody lub innej metody, z wyjątkiem Konstruktor pakietu VSPackage:  
  
    ```csharp  
    IVsActivityLog log = GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log == null) return;  
  
    int hr = log.LogEntry((UInt32)__ACTIVITYLOG_ENTRYTYPE.ALE_INFORMATION,  
        this.ToString(),  
        string.Format(CultureInfo.CurrentCulture,  
        "Called for: {0}", this.ToString()));  
    ```  
  
     Ten kod pobiera <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> usługi i rzutuje je na <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> interfejsu. <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog.LogEntry%2A> zapisuje wpis informacyjny w dzienniku aktywności w kontekście bieżącej kultury.  
  
2.  Podczas ładowania pakietu VSPackage (zazwyczaj podczas wywoływania polecenia lub okno jest otwarty), tekst został napisany z dziennikiem aktywności.  
  
## <a name="to-examine-the-activity-log"></a>Aby sprawdzić dziennik aktywności  
  
1.  Uruchom program Visual Studio z [/Log](../ide/reference/log-devenv-exe.md) przełącznik wiersza polecenia, aby zapisać plik ActivityLog.xml na dysku podczas sesji.

2.  Po zamknięciu programu Visual Studio, Znajdź dziennika aktywności w podfolderze dla danych programu Visual Studio: **% AppData %* \Microsoft\VisualStudio\15.0\ActivityLog.xml*.  
  
3.  Otwórz dziennik aktywności, za pomocą dowolnego edytora tekstów. Poniżej przedstawiono typowe wpis:  
  
    ```  
    Called for: Company.MyApp.MyAppPackage ...  
    ```  
  
## <a name="robust-programming"></a>Skuteczne programowanie  
 Ponieważ dziennik aktywności jest usługą, dziennik aktywności jest niedostępna w Konstruktorze pakietu VSPackage.  
  
 Dziennik aktywności powinna uzyskać tuż przed zapisu do niego. Nie w pamięci podręcznej lub dziennika aktywności do użytku w przyszłości.  
  
## <a name="see-also"></a>Zobacz także
 [/ Log (devenv.exe)](../ide/reference/log-devenv-exe.md)   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__ACTIVITYLOG_ENTRYTYPE>   
 [Rozwiązywanie problemów z pakietami VSPackage](../extensibility/troubleshooting-vspackages.md)   
 [Pakiety VSPackage](../extensibility/internals/vspackages.md)
