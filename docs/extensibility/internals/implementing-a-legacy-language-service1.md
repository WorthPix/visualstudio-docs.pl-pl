---
title: Implementowanie Service1 języka starszych | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, managed
ms.assetid: df638f24-166d-4b80-be82-c9c39ca7a556
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0486b8ad035d64f542d48f1e304413780958d90c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129339"
---
# <a name="implementing-a-legacy-language-service"></a>Wdrażanie usługi języka starsza wersja
Można klas w ramach zarządzanego pakietu (MPF) implementację usługi języka starszej wersji, która obsługuje wiele funkcji, takich jak wyróżnianie składni, pasujących nawiasów klamrowych i uzupełniania IntelliSense.  
  
 Usługi w starszej wersji języka są zaimplementowane jako część pakiet VSPackage, ale jest nowsza sposób implementowania funkcji usługi języka Aby korzystać z rozszerzeń MEF. Aby dowiedzieć się więcej o nowy sposób wdrożenia usługi języka, zobacz [edytora i rozszerzenia usługi języka](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Zaleca się zacząć Edytor nowy interfejs API tak szybko, jak to możliwe. Spowoduje to poprawić wydajność usługi języka i pozwala korzystać z nowych funkcji edytora.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Omówienie starszej wersji usługi językowej](../../extensibility/internals/legacy-language-service-overview.md)  
 Przegląd funkcji usługi języka, które są obsługiwane w MPF.  
  
 [Wdrażanie usługi języka starsza wersja](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
 W tym artykule opisano, co jest wymagane do wdrożenia usługi języka przy użyciu MPF.  
  
 [Zarejestrowanie starsza wersja usługi języka](../../extensibility/internals/registering-a-legacy-language-service1.md)  
 W tym artykule opisano kroki, które są wymagane do zarejestrowania usługi języka MPF z [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Analizator i skaner starszej wersji usługi językowej](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)  
 W tym artykule opisano dwa analizatory składni, które są wymagane do wdrożenia przy użyciu MPF wszystkich funkcji usługi języka.  
  
 [Przewodnik: tworzenie starszej wersji usługi językowej](../../extensibility/internals/walkthrough-creating-a-legacy-language-service.md)  
 Zawiera podstawowe kroki, które są wymagane do wdrożenia usługi języka MPF w pakiet VSPackage.  
  
 [Przewodnik: pobieranie listy zainstalowanych fragmentów kodu (starsza wersja implementacji)](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md)  
 Prezentuje techniki pobierania listy fragmentów kodu zainstalowane.  
  
 [Funkcje usługi starszej wersji języka](../../extensibility/internals/legacy-language-service-features1.md)  
 Zawiera łącza do tematów w tym szczegółów, co należy wykonać w celu wdrożenia wszystkich funkcji usługi języka przy użyciu MPF.