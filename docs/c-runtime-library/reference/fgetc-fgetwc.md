---
title: fgetc, fgetwc
ms.date: 11/04/2016
apiname:
- fgetwc
- fgetc
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
- _fgettc
- fgetwc
- fgetc
helpviewer_keywords:
- fgettc function
- characters, reading
- _fgettc function
- fgetc function
- streams, reading characters from
- reading characters from streams
- fgetwc function
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
ms.openlocfilehash: a853a46fc43106c9ea57be84b37fb46a18041ba8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334007"
---
# <a name="fgetc-fgetwc"></a>fgetc, fgetwc

Liest ein Zeichen aus einem Stream

## <a name="syntax"></a>Syntax

```C
int fgetc(
   FILE *stream
);
wint_t fgetwc(
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

**Fgetc** gibt das gelesene Zeichen als ein **Int** fest oder gibt **EOF** auf einen Fehler oder ein Dateiende anzugeben. **Fgetwc** zurückgegeben wird, als eine [Wint_t](../../c-runtime-library/standard-types.md), das Breitzeichen, die das gelesene Zeichen entspricht, oder gibt **WEOF** auf einen Fehler oder ein Dateiende anzugeben. Verwenden Sie für beide Funktionen **Feof** oder **Ferror** ein Fehler auftritt und eine End-of-File-Bedingung unterscheiden. Wenn ein Lesefehler auftritt, wird der Fehlerindikator für den Stream festgelegt. Wenn *Stream* ist **NULL**, **Fgetc** und **Fgetwc** der Handler für ungültige Parameter aufgerufen, siehe [Parameter Überprüfung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** zu **EINVAL** und zurückgeben **EOF**.

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen liest ein einzelnes Zeichen von der aktuellen Position der Datei zugeordneten *Stream*. Die Funktion erhöht dann den zugeordneten Dateizeiger (sofern definiert), um auf das nächste Zeichen zu zeigen. Wenn der Stream am Dateiende ist, wird der Dateiende-Indikator für den Stream festgelegt.

**Fgetc** entspricht **Getc**, jedoch nur als Funktion anstelle einer Funktion und Makro implementiert.

**Fgetwc** ist die Breitzeichen-Version von **Fgetc**; er liest **c** als Multibytezeichen oder Breitzeichen, je nachdem, ob *Stream* im geöffnet ist im Textmodus oder Binärmodus.

Die Versionen mit dem Suffix **_nolock** sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt.

Weitere Informationen zur Verarbeitung von Breitzeichen und Multibytezeichen im Text- und Binärmodus finden Sie unter [Unicodestream-E/A im Text- und Binärmodus](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgettc**|**fgetc**|**fgetc**|**fgetwc**|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fgetc**|\<stdio.h>|
|**fgetwc**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fgetc.c
// This program uses getc to read the first
// 80 input characters (or until the end of input)
// and place them into a string named buffer.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   char buffer[81];
   int  i, ch;

   // Open file to read line from:
   fopen_s( &stream, "crt_fgetc.txt", "r" );
   if( stream == NULL )
      exit( 0 );

   // Read in first 80 characters and place them in "buffer":
   ch = fgetc( stream );
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )
   {
      buffer[i] = (char)ch;
      ch = fgetc( stream );
   }

   // Add null to end string
   buffer[i] = '\0';
   printf( "%s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crtfgetctxt"></a>Eingabe: crt_fgetc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Output

```Output
Line one.
Line two.
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
