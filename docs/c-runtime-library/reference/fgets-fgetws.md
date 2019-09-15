---
title: fgets, fgetws
ms.date: 07/11/2018
api_name:
- fgets
- fgetws
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
- _fgetts
- fgetws
- fgets
helpviewer_keywords:
- _fgetts function
- streams, getting strings from
- streams, reading from
- fgets function
- fgetws function
- fgetts function
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
ms.openlocfilehash: 3f68bee181ebb20eb7a0a2eaca02a72c4dc03616
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957398"
---
# <a name="fgets-fgetws"></a>fgets, fgetws

Ruft eine Zeichenfolge aus einem Stream ab

## <a name="syntax"></a>Syntax

```C
char *fgets(
   char *str,
   int numChars,
   FILE *stream
);
wchar_t *fgetws(
   wchar_t *str,
   int numChars,
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Speicherort für Daten.

*numChars*<br/>
Die maximale Anzahl der zu lesenden Zeichen

*stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt *Str*zurück. **Null** wird zurückgegeben, um einen Fehler oder eine dateiendebedingung anzugeben. Verwenden Sie **feof** oder **ferror** , um zu bestimmen, ob ein Fehler aufgetreten ist. Wenn *Str* oder *Stream* ein NULL-Zeiger ist, oder wenn *NumChars* kleiner oder gleich NULL ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird **errno** auf **EINVAL** festgelegt, und die Funktion gibt **null**zurück.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Funktion "** Funktion" liest eine Zeichenfolge aus dem eingabestreamargument und speichert Sie in *Str*. **fgets** liest Zeichen von der aktuellen Streamposition in und einschließlich des ersten Zeilen Vorzeichens, bis zum Ende des Streams oder bis die Anzahl der gelesenen Zeichen gleich *NumChars* -1 ist, je nachdem, was zuerst eintritt. Das in *Str* gespeicherte Ergebnis wird mit einem NULL-Zeichen versehen. Das Zeilenumbruchzeichen wird, wenn es gelesen wird, in die Zeichenfolge aufgenommen.

" **f** " ist eine breit Zeichen Version von " **f**".

**fgetws** liest das breit Zeichen Argument *Str* als multibyte-Zeichenfolge oder Zeichenfolge mit breit Zeichen, je nachdem, ob der *Stream* im Textmodus oder Binärmodus geöffnet ist. Weitere Informationen zur Anwendung von Text- und Binärmodi in Unicode- und Multibyte-Stream-E/A finden Sie unter [Text- und Binärmodusdatei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [Unicodestream-E/A im Text- und Binärmodus](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgetts**|**fgets**|**fgets**|**fgetws**|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fgets**|\<stdio.h>|
|**fgetws**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fgets.c
// This program uses fgets to display
// the first line from a file.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char line[100];

   if( fopen_s( &stream, "crt_fgets.txt", "r" ) == 0 )
   {
      if( fgets( line, 100, stream ) == NULL)
         printf( "fgets error\numChars" );
      else
         printf( "%s", line);
      fclose( stream );
   }
}
```

### <a name="input-crt_fgetstxt"></a>Eingabe: crt_fgets.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Ausgabe

```Output
Line one.
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
