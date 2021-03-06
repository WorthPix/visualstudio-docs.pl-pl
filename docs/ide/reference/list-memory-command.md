---
title: Lista pamięci — Polecenie
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.listmemory
helpviewer_keywords:
- Debug.ListMemory command
- ListMemory command
- list memory command
ms.assetid: a84de361-a6a6-4f6d-96aa-a0d4a424371e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9f3ce3aee4a7a498600da4eb0c99210c9c20d00f
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2018
ms.locfileid: "33703422"
---
# <a name="list-memory-command"></a>Lista pamięci — Polecenie
Wyświetla zawartość z pamięci podanego zakresu.

## <a name="syntax"></a>Składnia

```cmd
Debug.ListMemory [/ANSI|Unicode] [/Count:number] [/Format:formattype]
[/Hex|Signed|Unsigned] [expression]
```

## <a name="arguments"></a>Argumenty
 `expression`

 Opcjonalna. Adres pamięci, z którego ma zostać rozpoczęta wyświetlanie pamięci.

## <a name="switches"></a>Przełączniki
 / ANSI&#124;Unicode

 Opcjonalna. Wyświetl pamięć jako znaków odpowiadającej liczbę bajtów pamięci, ANSI lub Unicode.

 / Liczba:`number`

 Opcjonalna. Określa liczbę bajtów pamięci, aby wyświetlić, zaczynając od `expression`.

 / Format:`formattype`

 Opcjonalna. Format typu podczas wyświetlania informacji w pamięci w **pamięci** okna; może być OneByte, TwoBytes, FourBytes, EightBytes, Float (32-bitowe) lub dwukrotnie (64-bitowe). Użycie OneByte `/Unicode` jest niedostępny.

 / Szesnastkowych&#124;podpisany&#124;bez znaku

 Opcjonalna. Określa format wyświetlania liczb: jak podpisem, bez znaku lub szesnastkową.

## <a name="remarks"></a>Uwagi
 Zamiast zapisywania pełnego **Debug.listmemory —** polecenie z wszystkich przełączników, można wywołać polecenia przy użyciu wstępnie zdefiniowane aliasy z przełącznikami, niektórych ustawień do określonej wartości. Na przykład zamiast wprowadzania:

```cmd
>Debug.ListMemory /Format:float /Count:30 /Unicode
```

 Można napisać:

```cmd
>df /Count:30 /Unicode
```

 Poniżej przedstawiono listę dostępnych aliasów dla **Debug.listmemory —** polecenia:

|Alias|Polecenia i przełączniki|
|-----------|--------------------------|
|**d**|Debug.listmemory —|
|**da**|Debug.listmemory — /Ansi|
|**bazy danych**|Debug.listmemory — /Format:OneByte|
|**Kontroler domeny**|Debug.listmemory — /Format:FourBytes /Ansi|
|**dd**|Debug.listmemory — /Format:FourBytes|
|**DF**|Debug.listmemory — /Format:Float|
|**dq —**|Debug.listmemory — /Format:EightBytes|
|**du**|Debug.listmemory — /Unicode|

## <a name="example"></a>Przykład

```cmd
>Debug.ListMemory /Format:float /Count:30 /Unicode
```

## <a name="see-also"></a>Zobacz też

- [Lista stosu wywołań, polecenie](../../ide/reference/list-call-stack-command.md)
- [Lista wątków, polecenie](../../ide/reference/list-threads-command.md)
- [Visual Studio — polecenia](../../ide/reference/visual-studio-commands.md)
- [Okno Polecenie](../../ide/reference/command-window.md)
- [Find/Command — pole](../../ide/find-command-box.md)
- [Visual Studio — aliasy poleceń](../../ide/reference/visual-studio-command-aliases.md)