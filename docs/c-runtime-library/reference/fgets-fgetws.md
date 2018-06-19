---
title: fgets, fgetws | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fgets
- fgetws
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
- _fgetts
- fgetws
- fgets
dev_langs:
- C++
helpviewer_keywords:
- _fgetts function
- streams, getting strings from
- streams, reading from
- fgets function
- fgetws function
- fgetts function
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e92deea033443ec942895d2aef2d1a307ac89f34
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402019"
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

*NumChars*<br/>
Die maximale Anzahl der zu lesenden Zeichen

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt *str*. **NULL** wird zurückgegeben, um einen Fehler oder eine End-of-File-Bedingung anzugeben. Verwendung **Feof** oder **Ferror** um zu bestimmen, ob ein Fehler aufgetreten ist. Wenn *str* oder *Stream* ist ein null-Zeiger oder *NumChars* ist kleiner als oder gleich 0 ist, ruft diese Funktion den Handler für ungültige Parameter wie beschrieben in [ Überprüfen der Parameter](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** festgelegt ist, um **EINVAL** und die Funktion gibt **NULL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Fgets** -Funktion liest eine Zeichenfolge aus der Eingabe *Stream* Argument und speichert ihn in *str*. **Fgets** liest Zeichen aus die aktuelle Streamposition zu und einschließlich des ersten Zeilenumbruchzeichens bis zum Ende des Streams befindet, oder bis die Anzahl von Zeichen gelesen ist gleich *NumChars* - 1, je nachdem, was zuerst eintritt. Das Ergebnis gespeichert *str* mit einem Null-Zeichen angefügt. Das Zeilenumbruchzeichen wird, wenn es gelesen wird, in die Zeichenfolge aufgenommen.

**Fgetws** ist eine Breitzeichen-Version von **Fgets**.

**Fgetws** liest die breitzeichenargument *str* als Multibyte Zeichenfolge oder eine Breitzeichen-Zeichenfolge, je nachdem, ob *Stream* im Textmodus oder Binärmodus geöffnet ist bzw. Weitere Informationen zur Anwendung von Text- und Binärmodi in Unicode- und Multibyte-Stream-E/A finden Sie unter [Text- und Binärmodusdatei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [Unicodestream-E/A im Text- und Binärmodus](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

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
// a line from a file on the screen.
//

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

### <a name="input-crtfgetstxt"></a>Eingabe: crt_fgets.txt

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
