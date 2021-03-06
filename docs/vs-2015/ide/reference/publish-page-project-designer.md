---
title: Strona publikowania, Projektant projektu | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.PropertyPage
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Project Designer, Publish page
- Publish page in Project Designer
ms.assetid: 153527c6-8b95-4003-8e8e-03a489d0a629
caps.latest.revision: 37
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1dcd6660ff431bee76fb7f595ed243104136684d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49277969"
---
# <a name="publish-page-project-designer"></a>Strona publikowania, Projektant projektu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
**Publikuj** strony **projektanta projektu** służy do konfigurowania właściwości dla wdrażania ClickOnce.  
  
 Aby uzyskać dostęp do **Publikuj** wybierz węzeł projektu w **Eksploratora rozwiązań**, a następnie na **projektu** menu, kliknij przycisk **właściwości**. Podczas **projektanta projektu** zostanie wyświetlona, kliknij przycisk **publikowania** kartę.  
  
> [!NOTE]
>  Niektóre właściwości ClickOnce, opisane w tym miejscu można również ustawić **PublishWizard**, która jest dostępna z **kompilacji** menu lub przez kliknięcie przycisku **PublishWizard** przycisk na to Strona.  
  
## <a name="uielement-list"></a>Lista elementów UI  
 **Lokalizacja folderu publikowania**  
 Określa lokalizację, w którym aplikacja została opublikowana. Może być ścieżką dysku (`C:\deploy\myapplication`), udział pliku (`\\server\myapplication`), serwer FTP (`ftp://ftp.microsoft.com/myapplication`), lub witryny sieci Web (`http://www.microsoft.com/myapplication`). Należy pamiętać, że tekst musi znajdować się w **lokalizację publikowania** polu w kolejności do przeglądania (**...** ) przycisku do pracy.  
  
 Domyślnie jest lokalizacja publikowania `http://localhost/<projectname>/` Jeśli usługi IIS są zainstalowane, lub `publish\` katalogu, jeśli nie masz zainstalowane usługi IIS. Jeśli na komputerze jest uruchomiony Windows Vista, wartość domyślna to zawsze `publish\` katalogu, niezależnie od tego, czy zostały zainstalowane usługi IIS.  
  
 **Adres URL folderu instalacji**  
 Opcjonalna. Określa witryny sieci Web, do której przejdzie do zainstalowania aplikacji. Jest to konieczne, tylko gdy różni się od **lokalizację publikowania**, na przykład, jeśli aplikacja została opublikowana serwer przejściowy.  
  
 **Tryb i ustawienia instalacji**  
 Określa, czy aplikacja jest uruchamiana bezpośrednio z **lokalizację publikowania** (gdy **aplikacja jest dostępna online tylko** wybrano) lub jest zainstalowana i dodać do **Start**  menu i **apletu Dodaj lub usuń programy** elementu w **Panelu sterowania** (gdy **aplikacja jest dostępna w trybie offline oraz** jest zaznaczona).  
  
 Aplikacje przeglądarki WPF sieci Web, aby uzyskać **aplikacja jest dostępna w trybie offline oraz** opcja jest wyłączona, ponieważ takie aplikacje są dostępne tylko w trybie online.  
  
 **Pliki aplikacji**  
 Otwiera [pliki aplikacji, okno dialogowe](http://msdn.microsoft.com/en-us/b06dff3a-b87a-4caf-996b-7a4acf8137a8), który jest używany do określenia, jak i gdzie poszczególne pliki są instalowane.  
  
 **Wymagania wstępne**  
 Otwiera [wstępnie wymagane składniki, okno dialogowe](../../ide/reference/prerequisites-dialog-box.md), który jest używany do określenia wstępnie wymagane składniki, takie jak .NET Framework, można zainstalować wraz z aplikacją.  
  
 **Aktualizacje**  
 Otwiera [dialogowym aktualizacje aplikacji](http://msdn.microsoft.com/en-us/8eca8743-8e68-4d04-bfd5-4dc0a9b2934f), która umożliwia określenie zachowania aktualizacji dla aplikacji. Nie jest dostępna, gdy **aplikacja jest dostępna online tylko** jest zaznaczone.  
  
 **Opcje**  
 Otwiera [okno dialogowe Opcje publikowania](http://msdn.microsoft.com/en-us/fd9baa1b-7311-4f9e-8ffb-ae50cf110592), który jest używany do określenia dodatkowych zaawansowane opcje publikowania.  
  
 **Opublikuj wersję**  
 Ustawia numer wersji publikowania dla aplikacji; Po zmianie numeru wersji, aplikacja została opublikowana jako aktualizację. Każda część wersję publikacji (**głównych**, **pomocnicza**, **kompilacji**, **poprawki**) może mieć maksymalną wartość 65355 (<xref:System.UInt16.MaxValue>), Maksymalna dozwolona przez <xref:System.Version>.  
  
 Po zainstalowaniu więcej niż jedna wersja aplikacji przy użyciu technologii ClickOnce, instalacja przemieszcza inne wersje aplikacji do folderu o nazwie archiwum, w lokalizacji publikowania, który określisz. Archiwizowanie starszych w ten sposób utrzymuje katalogu instalacyjnyego folderów z wcześniejszych wersji.  
  
 **Automatycznie zwiększ numer poprawki przy każdej publikacji**  
 Opcjonalna. Po wybraniu tej opcji (ustawienie domyślne), **poprawki** część numeru wersji publikowania jest zwiększany o jeden każdym opublikowaniu aplikacji. To powoduje, że aplikacja opublikowana jako aktualizację.  
  
 **Kreator publikacji**  
 Otwiera [Kreator publikacji](http://msdn.microsoft.com/en-us/fc6abebd-13d6-48e4-a567-fbc52dad0872). Kończenie pracy Kreatora publikacji ma taki sam skutek jak działa **Publikuj** polecenie **kompilacji** menu.  
  
 **Publikuj teraz**  
 Publikuje aplikacji przy użyciu bieżących ustawień. Odpowiednikiem **Zakończ** znajdujący się w **PublishWizard**.  
  
## <a name="see-also"></a>Zobacz też  
 [Publikowanie aplikacji ClickOnce](../../deployment/publishing-clickonce-applications.md)   
 [Porady: publikowanie aplikacji ClickOnce za pomocą Kreatora publikacji](../../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Porady: Określanie lokalizacji kopiowania plików w programie Visual Studio](../../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [Porady: Określanie lokalizacji, w której użytkownicy końcowi będą przeprowadzać instalacje](../../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)   
 [Porady: Określanie Linku do pomocy technicznej](../../deployment/how-to-specify-a-link-for-technical-support.md)   
 [Porady: Określanie ClickOnce w trybie Offline lub Online instalowania tryb](../../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)   
 [Porady: włączenie funkcji AutoStart dla instalacji z dysku CD](../../deployment/how-to-enable-autostart-for-cd-installations.md)   
 [Porady: ustawienie ClickOnce wersji publikacji](../../deployment/how-to-set-the-clickonce-publish-version.md)   
 [Porady: automatyczne zwiększenie ClickOnce wersji publikacji](../../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [Porady: Określanie plików publikowanych za pomocą technologii ClickOnce](../../deployment/how-to-specify-which-files-are-published-by-clickonce.md)   
 [Porady: Instalowanie wymagań wstępnych przy użyciu aplikacji ClickOnce](../../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [Porady: Zarządzanie aktualizacji dla aplikacji ClickOnce](../../deployment/how-to-manage-updates-for-a-clickonce-application.md)   
 [Porady: zmiana języka publikacji dla aplikacji ClickOnce](../../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)   
 [Porady: Określanie nazwy Menu Start dla aplikacji ClickOnce](../../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)   
 [Porady: określanie strony publikowania dla aplikacji ClickOnce](../../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)   
 [Wskazówki dotyczące wdrażania i zabezpieczeń ClickOnce](../../deployment/clickonce-security-and-deployment.md)



