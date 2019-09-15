---
title: _fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l
ms.date: 11/04/2016
api_name:
- _fwprintf_p
- _fprintf_p_l
- _fwprintf_p_l
- _fprintf_p
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
- _fprintf_p
- _ftprintf_p
- fwprintf_p
- _fwprintf_p
- fprintf_p
- ftprintf_p
helpviewer_keywords:
- fprintf_p_l function
- fprintf_p function
- _fprintf_p_l function
- _fprintf_p function
- _ftprintf_p_l function
- streams, printing formatted data to
- _fwprintf_p function
- fwprintf_p function
- _ftprintf_p function
- _fwprintf_p_l function
- ftprintf_p function
- printing [C++], formatted data to streams
- ftprintf_p_l function
- fwprintf_p_l function
ms.assetid: 46b082e1-45ba-4383-9ee4-97015aa50bc6
ms.openlocfilehash: 6509aba4097b3b37443443b533ebd9fb92c923a1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957001"
---
# <a name="_fprintf_p-_fprintf_p_l-_fwprintf_p-_fwprintf_p_l"></a>_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l

Gibt formatierte Daten an einen Stream aus

## <a name="syntax"></a>Syntax

```C
int _fprintf_p(
   FILE *stream,
   const char *format [,
   argument ]...
);
int _fprintf_p_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument ]...
);
int _fwprintf_p(
   FILE *stream,
   const wchar_t *format [,
   argument ]...
);
int _fwprintf_p_l(
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

**_fprintf_p** und **_fwprintf_p** geben die Anzahl der geschriebenen Zeichen zurück oder geben einen negativen Wert zurück, wenn ein Ausgabefehler auftritt.

## <a name="remarks"></a>Hinweise

**_fprintf_p** formatiert und druckt eine Reihe von Zeichen und Werten in den *Ausgabestream*. Jedes Funktions *Argument* (sofern vorhanden) wird entsprechend der entsprechenden Format Spezifikation im- *Format*konvertiert und ausgegeben. Für **_fprintf_p**weist das *Format* -Argument die gleiche Syntax auf und verwendet es in **_printf_p**. Diese Funktionen unterstützen Positionsparameter, d.h., dass die von der Formatzeichenfolge verwendete Parameterreihenfolge geändert werden kann. Weitere Informationen zu Positionsparametern finden Sie unter [printf_p-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md).

**_fwprintf_p** ist eine breit Zeichen Version von **_fprintf_p**. in **_fwprintf_p**ist *Format* eine Zeichenfolge mit breit Zeichen. Diese Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **_fprintf_p** unterstützt derzeit nicht die Ausgabe in einen Unicode-Stream.

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch den Gebiets Schema Parameter, der anstelle des aktuellen Gebiets Schemas übergeben wurde.

> [!IMPORTANT]
> Stellen Sie sicher, dass *format* keine benutzerdefinierte Zeichenfolge ist.

Wie die nicht sicheren Versionen (siehe [fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)) überprüfen diese Funktionen ihre Parameter und rufen den Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben, wenn entweder *Stream* oder  *Format* ist ein NULL-Zeiger oder, wenn unbekannte oder ungültige Formatierungsspezifizierer vorhanden sind. Wenn die weitere Ausführung zugelassen wird, geben die Funktionen-1 zurück und legen **errno** auf **EINVAL**fest.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_ftprintf_p**|**_fprintf_p**|**_fprintf_p**|**_fwprintf_p**|
|**_ftprintf_p_l**|**_fprintf_p_l**|**_fprintf_p_l**|**_fwprintf_p_l**|

Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_fprintf_p**, **_fprintf_p_l**|\<stdio.h>|
|**_fwprintf_p**, **_fwprintf_p_l**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fprintf_p.c
// This program uses _fprintf_p to format various
// data and print it to the file named FPRINTF_P.OUT. It
// then displays FPRINTF_P.OUT on the screen using the system
// function to invoke the operating-system TYPE command.
//

#include <stdio.h>
#include <process.h>

int main( void )
{
    FILE    *stream = NULL;
    int     i = 10;
    double  fp = 1.5;
    char    s[] = "this is a string";
    char    c = '\n';

    // Open the file
    if ( fopen_s( &stream, "fprintf_p.out", "w" ) == 0)
    {
        // Format and print data
        _fprintf_p( stream, "%2$s%1$c", c, s );
        _fprintf_p( stream, "%d\n", i );
        _fprintf_p( stream, "%f\n", fp );

        // Close the file
        fclose( stream );
    }

    // Verify our data
    system( "type fprintf_p.out" );
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
[printf_p-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l](cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)<br/>
[_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)<br/>
[printf_p-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)<br/>
