---
title: getchar, getwchar | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- getchar
- getwchar
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- getwchar
- GetChar
dev_langs:
- C++
helpviewer_keywords:
- gettchar function
- characters, reading
- getwchar function
- _gettchar function
- standard input, reading from
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ab9e7dfa0e42bcb6225917be991c43dd0f844da
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="getchar-getwchar"></a>getchar, getwchar

Liest ein Zeichen aus der Standardeingabe.

## <a name="syntax"></a>Syntax

```C
int getchar();
wint_t getwchar();
```

## <a name="return-value"></a>Rückgabewert

Gibt das gelesene Zeichen zurück. Zur Angabe eines Lesefehler oder End-of-File-Bedingung **Getchar** gibt **EOF**, und **Getwchar** gibt **WEOF**. Für **Getchar**, verwenden Sie **Ferror** oder **Feof** Fehler- oder dateiendeüberprüfung überprüfen.

## <a name="remarks"></a>Hinweise

Jede Routine liest ein einzelnes Zeichen aus **Stdin** und erhöht den zugeordneten Dateizeiger, um auf das nächste Zeichen zu zeigen. **GetChar** ist identisch mit [_fgetchar](fgetc-fgetwc.md), sondern es wird als Funktion und als Makro implementiert.

Diese Funktionen sperren den aufrufenden Thread und sind daher threadsicher. Eine nicht sperrende Version finden Sie unter [_getc_nolock _getwc_nolock](getchar-nolock-getwchar-nolock.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettchar**|**getchar**|**getchar**|**getwchar**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**getchar**|\<stdio.h>|
|**getwchar**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps der universellen Windows-Plattform (UWP) nicht unterstützt. Standardstream Handles, die mit der Konsole verknüpften sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in uwp-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_getchar.c
// Use getchar to read a line from stdin.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;

    for (i = 0; (i < 80) && ((ch = getchar()) != EOF)
                         && (ch != '\n'); i++)
    {
        buffer[i] = (char) ch;
    }

    // Terminate string with a null character
    buffer[i] = '\0';
    printf( "Input was: %s\n", buffer);
}
```

```Output

This textInput was: This text
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
