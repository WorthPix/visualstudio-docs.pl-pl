---
title: Obsługa stanu trwałości | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- state persistence, managed package framework support
- managed package framework, state persistence support
- state, persistence
ms.assetid: d25866f2-8d1f-477f-8aa5-3af3fbbf6e97
caps.latest.revision: 15
manager: douge
ms.openlocfilehash: 2b7eb294b38a5fb19303a175347adcdaa0f0ba22
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49242830"
---
# <a name="support-for-state-persistence"></a>Obsługa stanu trwałości
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] można zachować stanu obiektów. Na przykład właściwości rozwiązania i projektu zapisany i przywrócony z plików rozwiązania i projektu. Ustawienia użytkownika można eksportować do i zaimportowane z plików ustawień.  
  
 Pakietów VSPackage są zwykle oparte na magazynie lokalnym, w rejestrze systemu lub w folderze danych aplikacji dla bieżącego użytkownika lub komputera. Wartości, które wymagają małej ilości miejsca dla magazynu, na przykład liczby całkowite i ciągi znaków, są zazwyczaj przechowywane w rejestrze systemowym. Wartości, które wymagają dużej ilości miejsca do magazynowania, takie jak mapy bitowe, są zapisywane w pliku. Ścieżka do pliku sam można zapisać w rejestrze systemowym. Mechanizmu stanu trwałego musi mieć uprawnienia dostępu do lokalnego magazynu.  
  
## <a name="support-for-locating-local-storage"></a>Obsługa lokalizowanie magazynu lokalnego  
 <xref:Microsoft.VisualStudio.Shell.Package> Klasy zapewnia obsługę do lokalizowania informacji o stanie w rejestrze lub aplikacji danych folderze system dla bieżącego użytkownika lub komputera.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>  
 Zwraca ścieżkę katalogu głównego rejestru na komputerze lokalnym dla [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], na przykład HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\8.0Exp.  
  
 Katalog główny rejestru lokalnych są uzyskiwane z <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell> usługi. Jeśli ta opcja jest niedostępna, jest uzyskiwana z <xref:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute> atrybut pakietu VSPackage.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>  
 Zwraca ścieżkę bieżącego użytkownika (na komputer) katalogu głównego rejestru dla [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], na przykład HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp.  
  
 Katalog główny rejestru lokalnych są uzyskiwane z <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell> usługi. Jeśli ta opcja jest niedostępna, otrzymuje się od atrybutu DefaultLocalRegistryRoot pakietu VSPackage.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserDataPath%2A>  
 Zwraca ścieżkę katalogu, który służy jako wspólne repozytorium do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] danych dla bieżącego użytkownika mobilnego, na przykład C:\Documents and Settings\\*YourAccountName*\Application Data\Microsoft\ VisualStudio\8.0Exp.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserLocalDataPath%2A>  
 Zwraca ścieżkę katalogu, który służy jako wspólne repozytorium do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] danych dla bieżącego-mobilnego użytkownika, na przykład C:\Documents and Settings\\*YourAccountName*\Local Settings\Application Data\Microsoft\VisualStudio\8.0Exp.  
  
## <a name="see-also"></a>Zobacz też  
 [Stan pakietu VSPackage](../misc/vspackage-state.md)