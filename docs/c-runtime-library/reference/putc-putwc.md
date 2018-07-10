---
title: putc, putwc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- putwc
- putc
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
- _puttc
- putwc
- putc
dev_langs:
- C++
helpviewer_keywords:
- streams, writing characters to
- characters, writing
- putwc function
- putc function
- _puttc function
- puttc function
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 931a1a586f46327dd800ca5e1b2ef9a0b22f469d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404375"
---
# <a name="putc-putwc"></a>putc, putwc

Schreibt ein Zeichen in einen Stream.

## <a name="syntax"></a>Syntax

```C
int putc(
   int c,
   FILE *stream
);
wint_t putwc(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu schreibende Zeichen.

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Gibt das geschriebene Zeichen zurück. Um einen Fehler oder eine End-of-File-Bedingung anzugeben **Putc** und **Putchar** zurückgeben ** EOF`; **putwc` und **Putwchar** zurückgeben **WEOF**. Verwenden Sie bei allen vier Routinen [ferror](ferror.md) oder [feof](feof.md), um auf einen Fehler oder ein Dateiende zu prüfen. Wenn einen null-Zeiger übergeben wird, für die *Stream*, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **EOF** oder **WEOF** und **Errno** auf **EINVAL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Putc** -Routine schreibt das einzelne Zeichen *c* an die Ausgabe *Stream* an der aktuellen Position. Eine beliebige ganze Zahl übergeben werden kann, um **Putc**, aber es werden nur die unteren 8 Bits geschrieben. Die **Putchar** Routine ist identisch mit **Putc (** * c ***, "stdout")**. Wenn ein Lesefehler auftritt, wird für jede Routine die Fehleranzeige für den Stream festgelegt. **Putc** und **Putchar** ähneln **Fputc** und **_fputchar**, jedoch sowohl als Funktionen als auch als Makros implementiert werden (finden Sie unter [ Wahl zwischen Funktionen und Macros](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)). **Putwc** und **Putwchar** sind Breitzeichenversionen von **Putc** und **Putchar**zugeordnet. **Putwc** und **Putc** Verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **Putc** derzeit die Ausgabe in eine Unicode-Stream unterstützt keine.

Die Versionen mit dem Suffix **_nolock** sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt. Weitere Informationen finden Sie unter **_putc_nolock, _putwc_nolock**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_puttc**|**putc**|**putc**|**putwc**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**putc**|\<stdio.h>|
|**putwc**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps der universellen Windows-Plattform (UWP) nicht unterstützt. Standardstream Handles, die mit der Konsole verknüpften sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in uwp-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_putc.c
/* This program uses putc to write buffer
* to a stream. If an error occurs, the program
* stops before writing the entire buffer.
*/

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char *p, buffer[] = "This is the line of output\n";
   int  ch;

   ch = 0;
   /* Make standard out the stream and write to it. */
   stream = stdout;
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )
      ch = putc( *p, stream );
}
```

### <a name="output"></a>Ausgabe

```Output
This is the line of output
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
