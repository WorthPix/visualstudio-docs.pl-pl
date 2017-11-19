---
title: "Konfigurowanie sesji wydajności | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- common tasks, performance
- common tasks, profiling tools
- profiling tools, common tasks
- performance, gathering data
ms.assetid: e1c3ba41-ffca-4edf-9a7f-8a5a9244ef9b
caps.latest.revision: "36"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9bc896429c3d9e9307fd17a7727228770735af64
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2017
---
# <a name="configuring-performance-sessions"></a>Konfigurowanie sesji wydajności
Za pomocą [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] narzędziach profilowania mogą zbierać szeroką gamę dane wydajności dla wielu typów aplikacji. W tej sekcji przedstawiono sposób umożliwiają konfigurowanie narzędzi profilowania do zbierania danych interesującego Wizardand wydajności właściwości sesji wydajności i docelowy plik binarny. Profilowanie właściwości konfiguracji narzędzia mogą służyć do kontrolowania ilości danych są zbierane w przebiegu profilowania. Aby uzyskać więcej informacji, zobacz [kontrolowanie zbierania danych](../profiling/controlling-data-collection.md).  
  
> [!NOTE]
>  W wielu przypadkach przy użyciu domyślnych właściwości Kreatora osiągów to efektywny sposób zbierania danych profilowania. Aby uzyskać więcej informacji, zobacz [profilowanie wydajności — przewodnik dla początkujących](../profiling/beginners-guide-to-performance-profiling.md) i [wprowadzenie](../profiling/getting-started-with-performance-tools.md).  
  
## <a name="common-tasks"></a>Typowe zadania  
  
|Zadanie|Zawartość pokrewna|  
|----------|---------------------|  
|**Ustaw podstawowe opcje profilowania:** należy skonfigurować [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] do korzystania z serwera symboli firmy Microsoft. Będzie to upewnij się, że masz dostęp do symboli, takich jak nazwy funkcji i parametr, dla bieżącej wersji systemu Windows i innych aplikacji firmy Microsoft. Można również określić inne opcje ogólne, przed rozpoczęciem profilowania sesji, takie jak uprawnienia systemowe do narzędzi profilowania i nazw plików danych profilowania.|-   [Porady: odwołania informacji o symbolach systemu Windows](../profiling/how-to-reference-windows-symbol-information.md)<br />-   [Porady: Serializuj informacje dotyczące symboli](../profiling/how-to-serialize-symbol-information.md)<br />-   [Porady: Ustawianie bieżącej sesji](../profiling/how-to-set-the-current-session.md)<br />-   [Porady: Ustawianie uprawnień](../profiling/how-to-set-permissions.md)<br />-   [Porady: Ustawianie opcji nazwy pliku danych wydajności](../profiling/how-to-set-performance-data-file-name-options.md)|  
|**Określ dane, które mają być zbierane:** procedur, które są używane do konfigurowania sesję profilowania zależą od typ aplikacji docelowej, który ma zostać profilu i typu danych wydajności, które mają być zbierane.|-   [Porady: Wybieranie metod kolekcji](../profiling/how-to-choose-collection-methods.md)<br />-   [Zbieranie statystyk wydajności za pomocą metody pobierania próbek](../profiling/collecting-performance-statistics-by-using-sampling.md)<br />-   [Zbieranie alokacji pamięci .NET i okres istnienia obiektu](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Zbieranie szczegółowych danych o chronometrażu przy użyciu Instrumentacji](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)<br />-   [Porady: profilowanie kodu JavaScript na stronach sieci Web](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />-   [Zbieranie danych współbieżności procesu i wątku](../profiling/collecting-thread-and-process-concurrency-data.md)<br />-   [Zbieranie dodatkowych danych o wydajności](../profiling/collecting-additional-performance-data.md)|  
|**Ustawianie opcji konfiguracji zaawansowanej:** podczas profilu aplikacji .NET Framework, które ładują wielu wersji wspólnego języka środowiska wykonawczego języka wspólnego (CLR), można określić, którą wersję profilu. Jeśli masz wiele plików .exe w sesji wydajności, można ustawić kolejność uruchamiania plików binarnych.|-   [Porady: Określanie środowiska wykonawczego .NET Framework](../profiling/how-to-specify-the-dotnet-framework-runtime.md)<br />-   [Porady: Określanie plików binarnych do uruchomienia](../profiling/how-to-specify-the-binary-to-start.md)|  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Kontrolowanie zbierania danych](../profiling/controlling-data-collection.md)  
  
## <a name="see-also"></a>Zobacz też  
 [Eksplorator wydajności](../profiling/performance-explorer.md)