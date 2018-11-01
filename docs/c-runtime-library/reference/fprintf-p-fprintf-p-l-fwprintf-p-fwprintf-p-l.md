---
title: _fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l
ms.date: 11/04/2016
apiname:
- _fwprintf_p
- _fprintf_p_l
- _fwprintf_p_l
- _fprintf_p
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
apitype: DLLExport
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
ms.openlocfilehash: db9e9a746193c7bf35913d6792d87aa9ba85fa79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462776"
---
# <a name="fprintfp-fprintfpl-fwprintfp-fwprintfpl"></a>_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l

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

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

*format*<br/>
Formatsteuerzeichenfolge.

*Argument*<br/>
Optionale Argumente.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**_fprintf_p** und **_fwprintf_p** geben die Anzahl der geschriebenen Zeichen zurück, oder einen negativen Wert zurück, wenn ein Ausgabefehler auftritt.

## <a name="remarks"></a>Hinweise

**_fprintf_p** formatiert und gibt eine Reihe von Zeichen und Werten für die Ausgabe *Stream*. Jede Funktion *Argument* (sofern vorhanden) konvertiert und ausgegeben wird, entsprechend der jeweiligen Formatangabe in *Format*. Für **_fprintf_p**, *Format* Argument verfügt über die gleiche Syntax und Verwendung in **_printf_p**. Diese Funktionen unterstützen Positionsparameter, d.h., dass die von der Formatzeichenfolge verwendete Parameterreihenfolge geändert werden kann. Weitere Informationen zu Positionsparametern finden Sie unter [printf_p-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md).

**_fwprintf_p** ist eine Breitzeichen-Version von **_fprintf_p**in **_fwprintf_p**, *Format* ist eine Breitzeichen-Zeichenfolge. Diese Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **_fprintf_p** unterstützt derzeit keine Ausgabe in eine UNICODE-Stream.

Die Versionen dieser Funktionen mit den **_l** -Suffix sind beinahe identisch, außer dass sie den Locale-Parameter übergebenen Gebietsschemaparameter anstelle des aktuellen Gebietsschemas verwenden.

> [!IMPORTANT]
> Stellen Sie sicher, dass *format* keine benutzerdefinierte Zeichenfolge ist.

Wie bei den nicht sicheren Versionen (finden Sie unter [Fprintf, _fprintf_l, Fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)), diese Funktionen überprüfen ihre Parameter und der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md), wenn entweder *Stream* oder *Format* ein null-Zeiger ist oder wenn alle unbekannte oder ungültige Formatbezeichner vorhanden sind. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die Funktionen-1 zurück und legen Sie **Errno** zu **EINVAL**.

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
