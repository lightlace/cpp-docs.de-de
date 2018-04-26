---
title: getc, getwc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- getwc
- getc
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
- _gettc
- getwc
- _gettchar
- getc
dev_langs:
- C++
helpviewer_keywords:
- characters, reading
- _gettc function
- getwchar function
- streams, reading characters from
- reading characters from streams
- getc function
- getwc function
- gettc function
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 20845c8e1dbe24b30032cfb1fbffb5d24c6cfdc8
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="getc-getwc"></a>getc, getwc

Liest ein Zeichen aus einem Stream.

## <a name="syntax"></a>Syntax

```C
int getc(
   FILE *stream
);
wint_t getwc(
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*Stream*<br/>
Eingabestream

## <a name="return-value"></a>Rückgabewert

Gibt das gelesene Zeichen zurück. Zur Angabe eines Lesefehler oder End-of-File-Bedingung **Getc** gibt **EOF**, und **Getwc** gibt **WEOF**. Für **Getc**, verwenden Sie **Ferror** oder **Feof** Fehler- oder dateiendeüberprüfung überprüfen. Wenn *Stream* ist **NULL**, **Getc** und **Getwc** Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parameter Überprüfung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **EOF** (oder **WEOF** für **Getwc**), und legen **Errno** auf  **EINVAL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Jede Routine liest ein einzelnes Zeichen aus einer Datei an der aktuellen Position und erhöht den zugeordneten Dateizeiger (wenn definiert), um auf das nächste Zeichen zu zeigen. Die Datei zugeordnet ist *Stream*.

Diese Funktionen sperren den aufrufenden Thread und sind daher threadsicher. Eine nicht sperrende Version finden Sie unter [_getc_nolock _getwc_nolock](getc-nolock-getwc-nolock.md).

Es folgen routinespezifische Hinweise.

|Routine|Hinweise|
|-------------|-------------|
|**getc**|Identisch mit **Fgetc**, jedoch implementiert, als eine Funktion und eines Makros.|
|**getwc**|Breitzeichen Version von **Getc**. Liest ein Multibytezeichen oder Breitzeichen, je nachdem, ob *Stream* im Textmodus oder Binärmodus geöffnet ist.|

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettc**|**getc**|**getc**|**getwc**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**getc**|\<stdio.h>|
|**getwc**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_getc.c
// Use getc to read a line from a file.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;
    FILE* fp;

    // Read a single line from the file "crt_getc.txt".

    fopen_s(&fp, "crt_getc.txt", "r");
    if (!fp)
    {
       printf("Failed to open file crt_getc.txt.\n");
       exit(1);
    }

    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)
                         && (ch != '\n'); i++)
    {
        buffer[i] = (char) ch;
    }

    // Terminate string with a null character
    buffer[i] = '\0';
    printf( "Input was: %s\n", buffer);

    fclose(fp);
}
```

### <a name="input-crtgetctxt"></a>Eingabe: crt_getc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Ausgabe

```Output
Input was: Line one.
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
