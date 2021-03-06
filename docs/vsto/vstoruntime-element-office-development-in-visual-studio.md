---
title: '&lt;vstoruntime —&gt; — element (Office development w Visual Studio)'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <vstoRuntime> element
- <vstoRuntime> element
- vstoRuntime element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d21e097c0a05dfba2aa15bc41e37441ae02a63e4
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/05/2018
ms.locfileid: "34768069"
---
# <a name="ltvstoruntimegt-element-office-development-in-visual-studio"></a>&lt;vstoruntime —&gt; — element (Office development w Visual Studio)
  `vstoRuntime` Elementu `vstav3` przestrzeń nazw zawiera obsługiwanej wersji programu Visual Studio Tools for Office runtime dla konkretnego rozwiązania pakietu Office.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<vstoRuntime  
    release  
    version  
    supportUrl />  
```  
  
## <a name="elements-and-attributes"></a>Elementy i atrybuty  
 `vstoRuntime` Element jest wymagany i znajduje się w `vstav3` przestrzeni nazw. Jeśli rozwiązania do pakietu Office obsługuje dwie wersje programu Visual Studio Tools dla pakietu Office runtime, występują dwa `vstoRuntime` elementów w manifeście aplikacji.  
  
 `vstoRuntime` Element ma następujące atrybuty.  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`release`|Wymagana. Wydanej wersji programu Visual Studio Tools for Office runtime.|  
|`version`|Wymagana. Numer wersji Visual Studio Tools for Office runtime.|  
|`supportUrl`|Opcjonalna. Połącz z lokalizacji instalacji programu Visual Studio Tools for Office runtime.|  
  
 `vstoRuntime` nie ma żadnych elementów.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu pokazuje `vstoRuntime` elementu w manifeście aplikacji dla rozwiązań pakietu Office wdrożone za pomocą [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Ten przykładowy kod jest częścią większego przykładu udostępnionego w [manifesty aplikacji dla rozwiązań pakietu Office](../vsto/application-manifests-for-office-solutions.md).  
  
```xml  
<vstav3:vstoRuntime  
    release="VSTOR40Beta1"  
    version="10.0.20303"  
    supportUrl="http://www.microsoft.com" />  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Manifesty aplikacji dla rozwiązań pakietu Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty wdrożenia dla rozwiązań pakietu Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [Manifest aplikacji ClickOnce](/visualstudio/deployment/clickonce-application-manifest)  
  
  