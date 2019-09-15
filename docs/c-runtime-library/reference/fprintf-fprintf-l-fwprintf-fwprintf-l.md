---
title: fprintf, _fprintf_l, fwprintf, _fwprintf_l
ms.date: 11/04/2016
api_name:
- fwprintf
- fprintf
- _fprintf_l
- _fwprintf_l
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fprintf
- fwprintf
- _ftprintf
helpviewer_keywords:
- _fwprintf_l function
- fprintf function
- fprintf_l function
- _fprintf_l function
- _ftprintf function
- fwprintf function
- ftprintf_l function
- ftprintf function
- _ftprintf_l function
- print formatted data to streams
- fwprintf_l function
ms.assetid: 34a87e1c-6e4d-4d48-a611-58314dd4dc4b
ms.openlocfilehash: 1a296b8ac97a7f20a3834814c1ca3b7319720148
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956987"
---
# <a name="fprintf-_fprintf_l-fwprintf-_fwprintf_l"></a>fprintf, _fprintf_l, fwprintf, _fwprintf_l

Geben formatierte Daten an einen Stream aus Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md).

## <a name="syntax"></a>Syntax

```C
int fprintf(
   FILE *stream,
   const char *format [,
   argument ]...
);
int _fprintf_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument ]...
);
int fwprintf(
   FILE *stream,
   const wchar_t *format [,
   argument ]...
);
int _fwprintf_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale [,
   argument ]...
);
```

### <a name="parameters"></a>Parameter

*stream*<br/>
Zeiger auf die **FILE**-Struktur.

*format*<br/>
Formatsteuerzeichenfolge.

*argument*<br/>
Optionale Argumente.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

" **f** " gibt die Anzahl der geschriebenen Bytes zurück. " **f** " gibt die Anzahl der geschriebenen breit Zeichen zurück. Jede dieser Funktionen gibt stattdessen einen negativen Wert zurück, wenn ein Ausgabefehler auftritt. Wenn *Stream* oder *Format* **null**ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben die Funktionen-1 zurück und legen **errno** auf **EINVAL**fest. Die Format Zeichenfolge wird nicht auf gültige Formatierungszeichen wie bei Verwendung von **fprintf_s** oder **fwprintf_s**geprüft.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

**fprintf** formatiert und druckt eine Reihe von Zeichen und Werten in den *Ausgabestream*. Jedes Funktions *Argument* (sofern vorhanden) wird entsprechend der entsprechenden Format Spezifikation im- *Format*konvertiert und ausgegeben. Für **"f"** weist das *Format* -Argument die gleiche Syntax auf und verwendet es in **printf**.

" **swprintf** " ist eine breit Zeichen Version **von "f"** . in **"f"** ist *Format* eine Zeichenfolge mit breit Zeichen. Diese Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. die Ausgabe in einen Unicode-Stream wird von " **f printf** " derzeit nicht unterstützt.

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch den Gebiets Schema Parameter, der anstelle des aktuellen Thread Gebiets Schemas übergeben wurde.

> [!IMPORTANT]
> Stellen Sie sicher, dass *format* keine benutzerdefinierte Zeichenfolge ist.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ftprintf**|**fprintf**|**fprintf**|**fwprintf**|
|**_ftprintf_l**|**_fprintf_l**|**_fprintf_l**|**_fwprintf_l**|

Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fprintf**, **_fprintf_l**|\<stdio.h>|
|**fwprintf**, **_fwprintf_l**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fprintf.c
/* This program uses fprintf to format various
* data and print it to the file named FPRINTF.OUT. It
* then displays FPRINTF.OUT on the screen using the system
* function to invoke the operating-system TYPE command.
*/

#include <stdio.h>
#include <process.h>

FILE *stream;

int main( void )
{
   int    i = 10;
   double fp = 1.5;
   char   s[] = "this is a string";
   char   c = '\n';

   fopen_s( &stream, "fprintf.out", "w" );
   fprintf( stream, "%s%c", s, c );
   fprintf( stream, "%d\n", i );
   fprintf( stream, "%f\n", fp );
   fclose( stream );
   system( "type fprintf.out" );
}
```

```Output
this is a string
10
1.500000
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[Syntax der Formatangabe: printf- und wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
