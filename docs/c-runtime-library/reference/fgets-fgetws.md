---
title: fgets, fgetws
ms.date: 07/11/2018
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
helpviewer_keywords:
- _fgetts function
- streams, getting strings from
- streams, reading from
- fgets function
- fgetws function
- fgetts function
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
ms.openlocfilehash: 16dfb7cb0401083960669a735a976fbcd4ad4081
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489565"
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

*"NUMCHARS"*<br/>
Die maximale Anzahl der zu lesenden Zeichen

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt *str*. **NULL** wird zurückgegeben, um einen Fehler oder eine End-of-File-Bedingung anzugeben. Verwendung **Feof** oder **Ferror** zu bestimmen, ob ein Fehler aufgetreten ist. Wenn *str* oder *Stream* ist ein null-Zeiger oder *"NUMCHARS"* ist kleiner als oder gleich 0 (null), ruft diese Funktion den Handler für ungültige Parameter wie beschrieben in [ Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktion gibt **NULL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Fgets** Funktion liest eine Zeichenfolge, aus der Eingabe *Stream* Argument und speichert ihn in *str*. **Fgets** liest Zeichen aus der aktuellen Streamposition beginnend zu und einschließlich des ersten Zeilenumbruchzeichens am Ende des Streams oder bis die Anzahl von Zeichen gelesen ist gleich *"NUMCHARS"* - 1, je nachdem, was zuerst eintritt. Das Ergebnis gespeichert wird, im *str* mit einem Null-Zeichen angefügt. Das Zeilenumbruchzeichen wird, wenn es gelesen wird, in die Zeichenfolge aufgenommen.

**Fgetws** ist eine Breitzeichen-Version von **Fgets**.

**Fgetws** liest das breitzeichenargument *str* als eine Multibyte Zeichenfolge oder eine Zeichenfolge mit Breitzeichen je nachdem, ob *Stream* im Textmodus oder Binärmodus geöffnet ist bzw. Weitere Informationen zur Anwendung von Text- und Binärmodi in Unicode- und Multibyte-Stream-E/A finden Sie unter [Text- und Binärmodusdatei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [Unicodestream-E/A im Text- und Binärmodus](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

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

### <a name="input-crtfgetstxt"></a>Eingabe: crt_fgets.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Output

```Output
Line one.
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[gets, _getws](../../c-runtime-library/gets-getws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
