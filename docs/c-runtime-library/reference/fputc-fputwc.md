---
title: fputc, fputwc
ms.date: 11/04/2016
apiname:
- fputc
- fputwc
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
- fputc
- fputwc
- _fputtc
helpviewer_keywords:
- streams, writing characters to
- fputtc function
- _fputtc function
- fputwc function
- fputc function
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
ms.openlocfilehash: fc06c9f2060baae63071339768cef11fc5f34023
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288018"
---
# <a name="fputc-fputwc"></a>fputc, fputwc

Schreibt ein Zeichen in einen Stream.

## <a name="syntax"></a>Syntax

```C
int fputc(
   int c,
   FILE *stream
);
wint_t fputwc(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu schreibende Zeichen.

*stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt das geschriebene Zeichen zurück. Für **Fputc**, einen Rückgabewert von **EOF** gibt einen Fehler an. Für **Fputwc**, einen Rückgabewert von **WEOF** gibt einen Fehler an. Wenn *Stream* ist **NULL**, rufen diese Funktionen den Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben sie zurück **EOF** und **Errno** zu **EINVAL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen schreibt das einzelne Zeichen *c* in eine Datei an der Position durch die dazugehörige dateipositionsanzeige (sofern definiert) und verschieben den Indikator entsprechend. Im Fall von **Fputc** und **Fputwc**, die Datei zugeordnet ist *Stream*. Wenn die Datei keine Positionierungsanforderungen unterstützt oder im Append-Modus geöffnet wurde, wird das Zeichen am Ende des Streams angefügt.

Die zwei Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **Fputc** unterstützt derzeit keine Ausgabe in eine UNICODE-Stream.

Die Versionen mit dem Suffix **_nolock** sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt. Weitere Informationen finden Sie unter [_fputc_nolock, _fputwc_nolock](fputc-nolock-fputwc-nolock.md).

Es folgen routinespezifische Hinweise.

|-Routine zurückgegebener Wert|Hinweise|
|-------------|-------------|
|**fputc**|Äquivalent zu **Putc**, jedoch nur als Funktion anstelle einer Funktion und Makro implementiert.|
|**fputwc**|Breitzeichen Version von **Fputc**. Schreibt *c* als Multibytezeichen oder Breitzeichen, je nachdem, ob *Stream* im Textmodus oder Binärmodus geöffnet ist.|

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputtc**|**fputc**|**fputc**|**fputwc**|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fputc**|\<stdio.h>|
|**fputwc**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps für universelle Windows-Plattform (UWP) nicht unterstützt. Die mit der Konsole verknüpften standardstreamhandles,**Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in UWP-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fputc.c
// This program uses fputc
// to send a character array to stdout.

#include <stdio.h>

int main( void )
{
   char strptr1[] = "This is a test of fputc!!\n";
   char *p;

   // Print line to stream using fputc.
   p = strptr1;
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;

}
```

```Output
This is a test of fputc!!
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
