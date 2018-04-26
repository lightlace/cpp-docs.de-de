---
title: _getchar_nolock, _getwchar_nolock | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _getchar_nolock
- _getwchar_nolock
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
apitype: DLLExport
f1_keywords:
- getwchar_nolock
- _getwchar_nolock
- _getchar_nolock
- getchar_nolock
dev_langs:
- C++
helpviewer_keywords:
- _getwchar_nolock function
- getwchar_nolock function
- characters, reading
- _getchar_nolock function
- getchar_nolock function
- standard input, reading from
ms.assetid: dc49ba60-0647-4ae9-aa9a-a0618b1666de
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b85a187f19059dbd2b9292bcfec3994645ad18fa
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="getcharnolock-getwcharnolock"></a>_getchar_nolock, _getwchar_nolock

Liest ein Zeichen aus der Standardeingabe.

## <a name="syntax"></a>Syntax

```C
int _getchar_nolock( void );
wint_t _getwchar_nolock( void );
```

## <a name="return-value"></a>Rückgabewert

Siehe [getchar, getwchar](getchar-getwchar.md).

## <a name="remarks"></a>Hinweise

**_getchar_nolock** und **_getwchar_nolock** sind identisch mit **Getchar** und **Getwchar** mit dem Unterschied, dass sie nicht vor Störungen durch andere geschützt sind Threads. Sie sind möglicherweise schneller, da kein Mehraufwand zur Sperrung anderer Threads erforderlich ist. Verwenden Sie diese Funktionen nur in threadsichere Kontexten wie z. B. in Singlethreadanwendungen oder in Fällen, in denen der aufrufende Bereich die Threadisolation bereits handhabt.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_gettchar_nolock**|**_getchar_nolock**|**_getchar_nolock**|**_getwchar_nolock**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_getchar_nolock**|\<stdio.h>|
|**_getwchar_nolock**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps der universellen Windows-Plattform (UWP) nicht unterstützt. Standardstream Handles, die mit der Konsole verknüpften sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in uwp-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_getchar_nolock.c
// Use _getchar_nolock to read a line from stdin.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;

    for (i = 0; (i < 80) && ((ch = _getchar_nolock()) != EOF)
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
