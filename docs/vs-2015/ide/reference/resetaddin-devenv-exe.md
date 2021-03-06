---
title: -ResetAddin (devenv.exe) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disable addin
- addin state
- reset addin
ms.assetid: 9e339c8d-d768-4d86-8f45-2f479fc8255b
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: df5fe62efd783551a483853543ddb30312e64c65
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49213671"
---
# <a name="resetaddin-devenvexe"></a>/ResetAddin (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Usuwa poleceń i polecenia interfejs użytkownika skojarzony z określonym dodatku.  
  
## <a name="syntax"></a>Składnia  
  
```  
Devenv /ResetAddin AddIn  
```  
  
## <a name="arguments"></a>Argumenty  
 `AddIn`  
 Opcjonalna. Nazwa polecenia dodatku.  
  
## <a name="remarks"></a>Uwagi  
 Domyślnie nazwa polecenia dodatku jest równa  *\<AddInSolutionName >*. Połącz *.\< AddInSolutionName >* i pojawia się w Connect.cs jako `commandName` parametru `Exec` metody. Nazwę polecenia można również sprawdzić, zaczynając wpisywanie nazwy dodatku w oknie polecenia w programie Visual Studio, a następnie wypełniając pozostałe za pomocą technologii Intellisense.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie uruchamia programu Visual Studio i zapobiega `MyAddin` dodatek podczas uruchamiania systemu.  
  
```  
Devenv.exe /ResetAddin MyAddin.Connect.MyAddin  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Dostosowywanie ustawień środowiska deweloperskiego w programie Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Przełączniki wiersza polecenia Devenv](../../ide/reference/devenv-command-line-switches.md)



