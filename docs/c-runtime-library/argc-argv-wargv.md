---
title: __argcist __argvist __wargv
description: Beschreibt die globalen Konstanten der Microsoft C-Lauf Zeit Bibliothek __argc, __argvund __wargv.
ms.date: 11/04/2016
api_name:
- __wargv
- __argv
- __argc
api_location:
- msvcrt120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __argv
- __argc
- __wargv
helpviewer_keywords:
- __argv
- __wargv
- __argc
ms.assetid: 17001b0a-04ad-4762-b3a6-c54847f02d7c
no-loc:
- __argc
- __argv
- __wargv
- main
- wmain
ms.openlocfilehash: 86a22a7391c7bde34d7734631a2970a45851dda3
ms.sourcegitcommit: e93f3e6a110fe38bc642055bdf4785e620d4220f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76123980"
---
# <a name="opno-loc__argc-opno-loc__argv-opno-loc__wargv"></a>__argcist __argvist __wargv

Die globale Variable `__argc` zählt die Anzahl von Befehlszeilenargumenten, die an das Programm übergeben werden. `__argv` ist ein Zeiger auf ein Array mit Einzelbytezeichen oder Multibyte-Zeichensätzen, die die Programmargumente enthalten, und `__wargv` ist ein Zeiger auf ein Array mit Breitzeichen-Zeichenfolgen, die die Programmargumente enthalten. Diese globalen Variablen stellen die Argumente für `main` oder `wmain` bereit.

## <a name="syntax"></a>Syntax

```C
extern int __argc;
extern char ** __argv;
extern wchar_t ** __wargv;
```

## <a name="remarks"></a>Hinweise

In einem Programm, das die Funktion `main` verwendet, werden `__argc` und `__argv` beim Programmstart über die Befehlszeile initialisiert, die zum Starten des Programms verwendet wird. Die Befehlszeile wird in einzelne Argumente analysiert, und Platzhalter werden erweitert. Das Zählen der Argumente wird `__argc` zugewiesen, die Argumentzeichenfolgen werden auf dem Heap zugeordnet, und ein Zeiger zum Array der Argumente wird `__argv` zugewiesen. In einem Programm, das für die Verwendung von Breitzeichen und einer `wmain`-Funktion kompiliert ist, werden die Argumente analysiert und Platzhalter als Breitzeichen-Zeichenfolgen erweitert. Außerdem wird ein Zeiger zum Array der Argumentzeichenfolgen zu `__wargv` zugewiesen.

Für portablen Code wird die Verwendung der an `main` übergebenen Argumente empfohlen, um die Befehlszeilenargumente in Ihrem Programm abzurufen.

### <a name="generic-text-routine-mappings"></a>Zuordnungen von generischen Text Routinen

|Tchar.h-Routine|_UNICODE nicht definiert|_UNICODE definiert|
|---------------------|---------------------------|-----------------------|
|`__targv`|`__argv`|`__wargv`|

## <a name="requirements"></a>-Anforderungen

|Globale Variable|Erforderlicher Header|
|---------------------|---------------------|
|`__argc`ist `__argv`ist `__wargv`|\<stdlib.h>, \<cstdlib> (C++)|

`__argc`, `__argv` und `__wargv` sind Microsoft-Erweiterungen. Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Globale Variablen](../c-runtime-library/global-variables.md)\
[main Funktion und BefehlszeilenargumenteC++()](../cpp/main-function-command-line-args.md)\
[Verwenden von wmain anstelle main](../cpp/using-wmain-instead-of-main.md)
