---
title: Locationtype — | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- LocationType enumeration
ms.assetid: d3e1eedc-bfd3-4c91-881b-d69565138d0f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fb46eb1c7477f93ed63dfc4424d881886c8d0c8f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
ms.locfileid: "31480007"
---
# <a name="locationtype"></a>LocationType
Wskazuje typ lokalizacji informacji zawartych w symbolu.  
  
## <a name="syntax"></a>Składnia  
  
```C++  
enum LocationType {   
   LocIsNull,  
   LocIsStatic,  
   LocIsTLS,  
   LocIsRegRel,  
   LocIsThisRel,  
   LocIsEnregistered,  
   LocIsBitField,  
   LocIsSlot,  
   LocIsIlRel,  
   LocInMetaData,  
   LocIsConstant,  
   LocTypeMax  
};  
```  
  
## <a name="elements"></a>Elementy  
 `LocIsNull`  
 Informacje o lokalizacji jest niedostępny.  
  
 `LocIsStatic`  
 Lokalizacja jest statyczne.  
  
 `LocIsTLS`  
 Lokalizacja jest lokalny magazyn wątków.  
  
 `LocIsRegRel`  
 Lokalizacja jest względna rejestru.  
  
 `LocIsThisRel`  
 Lokalizacja jest `this`— względna.  
  
 `LocIsEnregistered`  
 Lokalizacja znajduje się w rejestrze.  
  
 `LocIsBitField`  
 Lokalizacja jest polem bitowym.  
  
 `LocIsSlot`  
 Lokalizacja jest miejscem Microsoft języka pośredniego (MSIL).  
  
 `LocIsIlRel`  
 Lokalizacja jest względna MSIL.  
  
 `LocInMetaData`  
 Lokalizacja jest w metadanych.  
  
 `LocIsConstant`  
 Lokalizacja jest wartością stałą.  
  
 `LocTypeMax`  
 Liczba typów lokalizacji, w tym wyliczeniu.  
  
## <a name="remarks"></a>Uwagi  
 Właściwości dostępne dla [idiasymbol —](../../debugger/debug-interface-access/idiasymbol.md) interfejsu zależą od lokalizacji symbolu w pliku obrazu. Aby uzyskać więcej informacji, zobacz [lokalizacje symboli](../../debugger/debug-interface-access/symbol-locations.md).  
  
 To wyliczenie wartości są zwracane przez wywołanie do [IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md) metody.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: cvconst.h  
  
## <a name="see-also"></a>Zobacz też  
 [Wyliczenia i struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasymbol —](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)   
 [Lokalizacje symboli](../../debugger/debug-interface-access/symbol-locations.md)