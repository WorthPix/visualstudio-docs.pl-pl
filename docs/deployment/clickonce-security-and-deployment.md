---
title: Wdrażania i zabezpieczeń ClickOnce | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce deployment
- deploying applications [ClickOnce]
- ClickOnce deployment
- publishing, ClickOnce
ms.assetid: abab6d34-c3c2-45c1-a8b6-43c7d3131e7a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 70c90d70af60b6bd1f2399847447c1d49785ebb0
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2018
ms.locfileid: "39078429"
---
# <a name="clickonce-security-and-deployment"></a>Wdrażania i zabezpieczeń ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] jest to technologia wdrażania umożliwiająca tworzenie automatycznie aktualizowane aplikacje z systemem Windows, które można instalować i uruchamiać z interakcji z użytkownikiem minimalny. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zapewnia pełną obsługę publikowanie i aktualizowanie aplikacji wdrożonych przy użyciu technologii ClickOnce, jeśli opracowano Twoich projektów w języku Visual Basic i Visual C#. Aby dowiedzieć się, jak wdrażanie aplikacji Visual C++, zobacz [wdrożenie rozwiązania ClickOnce dla aplikacji Visual C++](/cpp/ide/clickonce-deployment-for-visual-cpp-applications).  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] wdrożenie pozwala pokonać trzy główne problemy we wdrożeniu:  
  
-   **Trudności podczas aktualizowania aplikacji.** Przy użyciu wdrożenia Instalatora systemu Microsoft Windows zawsze wtedy, gdy aplikacja zostanie zaktualizowana, użytkownik może zainstalować aktualizację, plik msp i zastosować je do zainstalowanego produktu; za pomocą [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] wdrożenia, możesz podać aktualizacje automatyczne. Są pobierane tylko te części aplikacji, które uległy zmianie, a następnie ponowna instalacja aplikacji pełne, zaktualizowane z nowego folderu side-by-side.  
  
-   **Wpływ na komputerze użytkownika.** Przy użyciu wdrożenia Instalatora Windows aplikacji często zależy od składników udostępnionych oraz o potencjalnych konfliktów wersji; za pomocą [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] wdrożenia, każda aplikacja jest niezależna i nie może kolidować z innymi aplikacjami.  
  
-   **Uprawnienia zabezpieczeń.** Wdrażanie za pomocą Instalatora Windows wymaga uprawnień administracyjnych, a także umożliwia tylko użytkownika standardowego instalacji; [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] wdrożenia innych niż administracyjne użytkownicy mogą zainstalować i przydziela tylko tych uprawnień zabezpieczeń dostępu kodu niezbędnych dla aplikacji.  
  
 W przeszłości te problemy spowodowane czasami deweloperów podjęcie decyzji, tworzenie aplikacji sieci Web zamiast aplikacji opartych na Windows obniżania oczekiwanego poziomu zaawansowanego interfejsu użytkownika w celu ułatwienia instalacji. Przy użyciu aplikacji wdrożonych za pomocą [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], może mieć najlepsze cechy obu technologii.  
  
## <a name="what-is-a-clickonce-application"></a>Co to jest aplikacja ClickOnce?  
 A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikacja jest dowolnym Windows Presentation Foundation (*XBAP*), Windows Forms (*.exe*), aplikacja konsoli (*.exe*), lub rozwiązania dla pakietu Office (*.dll*) opublikowanych przy użyciu [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] technologii. Możesz opublikować [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikację na trzy różne sposoby: ze strony sieci Web, z sieciowego udziału plików lub z nośnika, takich jak dysk CD-ROM. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikacji można zainstalować na komputerze użytkownika końcowego i uruchamiane lokalnie, nawet wtedy, gdy komputer jest w trybie offline lub może być uruchamiane w trybie tylko w trybie online bez konieczności instalowania żadnych trwale na komputerze użytkownika końcowego. Aby uzyskać więcej informacji, zobacz [Wybieranie strategii wdrażania ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikacje mogą być samoaktualizacji; także sprawdzać dla nowszych wersji, jak długo będą stają się dostępne i automatycznie zastąpić wszelkie zaktualizowane pliki. Deweloper może określić zachowanie aktualizacji; administrator sieci może także kontrolować Aktualizuj strategie, na przykład oznaczenie aktualizację jako wymagane. Aktualizacje można również wycofać do starszej wersji przez użytkownika końcowego lub przez administratora. Aby uzyskać więcej informacji, zobacz [Wybieranie strategii aktualizacji ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).  
  
 Ponieważ [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikacje są odizolowane, instalowanie i uruchamianie [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikacji nie można przerwać istniejących aplikacji. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikacje są niezależne; Każdy [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikacja jest zainstalowany i uruchamiane z bezpiecznego poszczególnych użytkowników, pamięci podręcznej dla aplikacji. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikacje są uruchamiane w strefach zabezpieczeń Internet lub Intranet. Jeśli to konieczne, aplikacja może zażądać uprawnień zabezpieczeń z podwyższonym poziomem uprawnień. Aby uzyskać więcej informacji, zobacz [aplikacji Secure ClickOnce](../deployment/securing-clickonce-applications.md).  
  
## <a name="how-clickonce-security-works"></a>Jak działają zabezpieczenia ClickOnce  
 Podstawowe [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zabezpieczenia są oparte na certyfikatach, zasady zabezpieczeń dostępu kodu i monit o udzielenie zaufania ClickOnce.  
  
### <a name="certificates"></a>Certyfikaty  
 Authenticode certyfikaty są używane do weryfikacji autentyczności wydawcy aplikacji. Za pomocą kodu Authenticode dla wdrożenia aplikacji, ClickOnce zapobiega szkodliwych program instytucja sama jako program wiarygodnego źródła ustanowione, godne zaufania. Opcjonalnie certyfikaty może również służyć do podpisania aplikacji i manifestów wdrożenia, ponieważ udowodnić, że pliki nie zostały naruszone. Aby uzyskać więcej informacji, zobacz [ClickOnce i podpis Authenticode](../deployment/clickonce-and-authenticode.md). Certyfikaty można również skonfigurować komputery klienckie, aby wyświetlić listę zaufanych wydawców. Jeśli aplikacja pochodzi z zaufanego wydawcę, może zostać zainstalowane bez interakcji z użytkownikiem. Aby uzyskać więcej informacji, zobacz [Przegląd wdrażania aplikacji zaufanego](../deployment/trusted-application-deployment-overview.md).  
  
### <a name="code-access-security"></a>Zabezpieczenia dostępu kodu  
 Kod dostępu secrity pomaga ograniczać dostęp do tego kodu do chronionych zasobów. W większości przypadków można wybrać strefy Internet lub lokalny Intranet, aby ograniczyć uprawnienia. Użyj **zabezpieczeń** strony w **ProjectDesigner** żądania strefy, które są odpowiednie dla aplikacji. Można również debugować aplikacje przy użyciu ograniczonych uprawnień do emulowania środowisko użytkownika końcowego. Aby uzyskać więcej informacji, zobacz [zabezpieczenia dostępu kodu dla aplikacji ClickOnce](../deployment/code-access-security-for-clickonce-applications.md).  
  
### <a name="clickonce-trust-prompt"></a>Monit o udzielenie zaufania ClickOnce  
 Jeśli aplikacja żąda więcej uprawnień niż zezwala na strefy, użytkownik końcowy może monit podjęcia decyzji o zaufaniu. Użytkownik końcowy można zdecydować, czy zaufane do uruchamiania aplikacji ClickOnce, takich jak aplikacje Windows Forms, aplikacji Windows Presentation Foundation, aplikacji konsoli, aplikacji przeglądarki XAML i rozwiązań dla pakietu Office. Aby uzyskać więcej informacji, zobacz [porady: Konfigurowanie funkcji ClickOnce zaufania monitowania](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md).  
  
## <a name="how-clickonce-deployment-works"></a>Jak działa wdrażania ClickOnce  
 Podstawowe [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] architektura wdrożenia opiera się na dwóch plikach manifestu XML: manifest aplikacji i manifest wdrożenia. Pliki są używane do opisywania zainstalowanym aplikacji ClickOnce z, jak są aktualizowane i kiedy są aktualizowane.  
  
### <a name="publish-clickonce-applications"></a>Publikowanie aplikacji ClickOnce  
 Manifest aplikacji zawiera opis samej aplikacji. W tym zestawy, zależności i plików, które tworzą aplikację, wymagane uprawnienia i lokalizację, w przypadku gdy aktualizacje będą dostępne. Deweloper aplikacji autorów manifest aplikacji za pomocą Kreatora publikacji w programie Visual Studio lub Manifest Generation i narzędzia do edytowania (*Mage.exe*) w [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Aby uzyskać więcej informacji, zobacz [porady: publikowanie aplikacji ClickOnce za pomocą Kreatora publikacji](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
 Manifest wdrożenia w tym artykule opisano sposób wdrażania aplikacji. Obejmuje to lokalizacja manifestu aplikacji i wersji aplikacji, uruchamianą klientów.  
  
### <a name="deploy-clickonce-applications"></a>Wdrażanie aplikacji ClickOnce  
 Po jego utworzeniu manifest wdrożenia jest kopiowany do lokalizacji wdrożenia. Może to być serwer sieci Web, sieciowego udziału plików lub nośników, takich jak dysk CD. Manifest aplikacji i wszystkich plików aplikacji są również kopiowane do lokalizacji wdrożenia, który jest określony w pliku manifestu wdrożenia. Może to być taka sama jak lokalizacja wdrożenia, lub można go z innej lokalizacji. Korzystając z **Kreatora publikacji** w programie Visual Studio, operacje kopiowania są wykonywane automatycznie.  
  
### <a name="install-clickonce-applications"></a>Instalowanie aplikacji ClickOnce  
 Po wdrożeniu w lokalizacji wdrożenia użytkownicy końcowi można pobrać i zainstalować aplikację, klikając ikony reprezentującej pliku manifestu wdrożenia, na stronie sieci Web lub w folderze. W większości przypadków użytkownik końcowy zobaczy proste okno dialogowe z pytaniem o potwierdzenie instalacji, po których instalacja będzie kontynuowana i aplikacja jest uruchamiana bez dodatkowej interwencji. W przypadkach, w której aplikacja wymaga podniesionych uprawnień lub jeżeli aplikacja nie jest podpisany przez zaufanego certyfikatu okno dialogowe prosi użytkownika o udzielenie uprawnień, zanim będzie można kontynuować instalacji. Chociaż instalacji ClickOnce są na użytkownika, podnoszenia poziomu uprawnień mogą być wymagane, jeśli istnieją wymagania wstępne, które wymagają uprawnień administratora. Aby uzyskać więcej informacji o podwyższonym poziomem uprawnień, zobacz [aplikacji ClickOnce Zabezpieczanie](../deployment/securing-clickonce-applications.md).  
  
 Certyfikaty jest zaufany na poziomie komputera lub przedsiębiorstwa, tak aby dyskretnie zainstalować aplikacji ClickOnce podpisane zaufanym certyfikatem. Aby uzyskać więcej informacji na temat zaufanych certyfikatów, zobacz [Przegląd wdrażania aplikacji zaufanego](../deployment/trusted-application-deployment-overview.md).  
  
 Aplikację można dodać do użytkownika **Start** menu i **apletu Dodaj lub usuń programy** w **Panelu sterowania**. W przeciwieństwie do innych technologii wdrażania, nic nie zostanie dodany do **Program Files** folder lub rejestru i nie prawa administracyjne są wymagane do instalacji  
  
> [!NOTE]
>  Istnieje również możliwość zapobiec aplikacji, z którego jest dodawany **Start** menu i **apletu Dodaj lub usuń programy** grupy, ułatwiając obowiązuje zachowują się jak aplikacja sieci Web. Aby uzyskać więcej informacji, zobacz [Wybieranie strategii wdrażania ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md).  
  
### <a name="update-clickonce-applications"></a>Aktualizowanie aplikacji ClickOnce  
 Deweloperzy aplikacji, tworząc zaktualizowaną wersję aplikacji, wygenerować nowy manifest aplikacji i skopiuj pliki do lokalizacji wdrożenia — zwykle równorzędny folder do folderu początkowego wdrożenia aplikacji. Administrator aktualizuje manifestu wdrażania, aby wskazać lokalizację nowej wersji aplikacji.  
  
> [!NOTE]
>  **Kreatora publikacji** w programie Visual Studio może służyć do wykonania tych kroków.  
  
 Oprócz lokalizacji wdrożenia manifest wdrożenia zawiera również lokalizacji aktualizacji (strony sieci Web lub udostępnianie plików sieciowych), gdzie aplikacja sprawdza, czy zaktualizowane wersje. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] **Publikowanie** właściwości są używane do określania, kiedy i jak często aplikacja ma sprawdzać dostępność aktualizacji. Zachowanie aktualizacji można określić w pliku manifestu wdrożenia lub może pojawić się w interfejsie użytkownika aplikacji przez użytkownika [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] interfejsów API. Ponadto **Publikuj** właściwości można zastosować do wprowadzania obowiązkowych aktualizacji lub wrócić do wcześniejszej wersji. Aby uzyskać więcej informacji, zobacz [Wybieranie strategii aktualizacji ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).  
  
### <a name="third-party-installers"></a>Instalatory innych firm  
 Można dostosować swój Instalatora ClickOnce, aby instalować składników innych firm oraz aplikacji. Konieczne jest posiadanie pakietu redystrybucyjnego (plik .exe i .msi) oraz opisano pakiet z manifestu produktu niezależny od języka i manifestu pakietu specyficzny dla języka. Aby uzyskać więcej informacji, zobacz [tworzenie pakietów programu inicjującego](../deployment/creating-bootstrapper-packages.md).  
  
## <a name="clickonce-tools"></a>Narzędzia ClickOnce  
 W poniższej tabeli przedstawiono narzędzia służącego do generowania, edytowania, zaloguj się i ponowne podpisywanie manifestów aplikacji i wdrożenia.  
  
|Narzędzie|Opis|  
|----------|-----------------|  
|[Strona zabezpieczeń, Projektant projektu](../ide/reference/security-page-project-designer.md)|Objawy manifestów aplikacji i wdrożenia.|  
|[Strona publikowania, Projektant projektu](../ide/reference/publish-page-project-designer.md)|Generuje i umożliwia edycję manifestów aplikacji i wdrożenia dla aplikacji Visual Basic i Visual C#.|  
|[*Mage.exe* (Manifest narzędzie generowania i edytowania)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)|Generuje manifestów aplikacji i wdrożenia dla aplikacji Visual Basic, Visual C# i Visual C++.<br /><br /> Podpisuje i podpisuje ponownie manifestów aplikacji i wdrożenia.<br /><br /> Można uruchomić z wiersza polecenia i skrypty usługi batch.|  
|[*MageUI.exe* (Manifest narzędzie, graficzny klient generowania i edytowania)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)|Generuje i umożliwia edycję manifestów aplikacji i wdrożenia.<br /><br /> Podpisuje i podpisuje ponownie manifestów aplikacji i wdrożenia.|  
|[Generateapplicationmanifest — zadanie](../msbuild/generateapplicationmanifest-task.md)|Generuje manifest aplikacji.<br /><br /> Można uruchomić z programu MSBuild. Aby uzyskać więcej informacji, zobacz [odwołanie do MSBuild](../msbuild/msbuild-reference.md).|  
|[Generatedeploymentmanifest — zadanie](../msbuild/generatedeploymentmanifest-task.md)|Generuje manifest wdrożenia.<br /><br /> Można uruchomić z programu MSBuild. Aby uzyskać więcej informacji, zobacz [odwołanie do MSBuild](../msbuild/msbuild-reference.md).|  
|[Signfile — zadanie](../msbuild/signfile-task.md)|Objawy manifestów aplikacji i wdrożenia.<br /><br /> Można uruchomić z programu MSBuild. Aby uzyskać więcej informacji, zobacz [odwołanie do MSBuild](../msbuild/msbuild-reference.md).|  
|<xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities>|Tworzenie własnych aplikacji można wygenerować manifestów aplikacji i wdrożenia.|  
  
 W poniższej tabeli przedstawiono wersja .NET Framework, wymagane do obsługi aplikacji ClickOnce w następujących przeglądarkach.  
  
|Przeglądarka|Wersja programu .NET Framework|  
|-------------|----------------------------|  
|Internet Explorer|W WERSJI 2.0, 3.0, 3.5, 3.5 Z DODATKIEM SP1, 4|  
|Firefox|W WERSJI 2.0 Z DODATKIEM SP1, 3.5 Z DODATKIEM SP1, 4|  
  
## <a name="see-also"></a>Zobacz także  
 [Wdrożenie ClickOnce w systemie Windows Vista](../deployment/clickonce-deployment-on-windows-vista.md)   
 [Publikowanie aplikacji ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Zabezpieczanie aplikacji ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Wdrażanie składników COM za pomocą technologii ClickOnce](../deployment/deploying-com-components-with-clickonce.md)   
 [Tworzenie aplikacji ClickOnce z wiersza polecenia](../deployment/building-clickonce-applications-from-the-command-line.md)   
 [Debugowanie aplikacji ClickOnce używających System.Deployment.Application](../deployment/debugging-clickonce-applications-that-use-system-deployment-application.md)