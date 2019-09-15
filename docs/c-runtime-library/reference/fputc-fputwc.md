---
title: fputc, fputwc
ms.date: 11/04/2016
api_name:
- fputc
- fputwc
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 3d289e54bca53be52d0b308d759f4200eca8599c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956959"
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

Jede dieser Funktionen gibt das geschriebene Zeichen zurück. Bei **fputc**deutet der Rückgabewert von **EOF** auf einen Fehler hin. Bei **fputwc**weist der Rückgabewert **WEOF** auf einen Fehler hin. Wenn der Stream **null**ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben Sie **EOF** zurück und legen **errno** auf **EINVAL**fest.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen schreibt das einzelne Zeichen *c* in eine Datei an der Position, die durch den zugehörigen Datei Positionsindikator angegeben wird (sofern definiert), und erhöht den Indikator nach Bedarf. Bei **fputc** und **fputwc**ist die Datei dem *Stream*zugeordnet. Wenn die Datei keine Positionierungsanforderungen unterstützt oder im Append-Modus geöffnet wurde, wird das Zeichen am Ende des Streams angefügt.

Die zwei Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **fputc** unterstützt derzeit keine Ausgabe in einen Unicode-Stream.

Die Versionen mit dem Suffix **_nolock** sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt. Weitere Informationen finden Sie unter [_fputc_nolock, _fputwc_nolock](fputc-nolock-fputwc-nolock.md).

Es folgen routinespezifische Hinweise.

|-Routine zurückgegebener Wert|Hinweise|
|-------------|-------------|
|**fputc**|Äquivalent zu **putc**, aber nur als Funktion und nicht als Funktion und Makro implementiert.|
|**fputwc**|Breit Zeichen Version von **fputc**. Schreibt *c* als Multibytezeichen oder breit Zeichen, je nachdem, ob der *Stream* im Textmodus oder im Binärmodus geöffnet ist.|

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputtc**|**fputc**|**fputc**|**fputwc**|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fputc**|\<stdio.h>|
|**fputwc**|\<stdio.h> oder \<wchar.h>|

Die-Konsole wird in universelle Windows-Plattform-Apps (UWP) nicht unterstützt. Die Standarddaten Strom Handles, die der Konsole –**stdin**, **stdout**und **stderr**– zugeordnet sind, müssen umgeleitet werden, bevor Sie von C-Lauf Zeitfunktionen in UWP-Apps verwendet werden können. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

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
