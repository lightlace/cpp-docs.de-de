---
title: _sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l
ms.date: 11/04/2016
apiname:
- _sprintf_p
- _swprintf_p_l
- _swprintf_p
- _sprintf_p_l
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
- _sprintf_p
- _swprintf_p_l
- _sprintf_p_l
- _swprintf_p
- sprintf_p
- swprint_p_l
- swprintf_p
- swprintf_p_l
helpviewer_keywords:
- sprintf_p_l function
- swprintf_p function
- swprintf_p_l function
- _sprintf_p function
- _sprintf_p_l function
- _swprintf_p function
- sprintf_p function
- _stprintf_p function
- stprintf_p function
- _swprintf_p_l function
- stprintf_p_l function
- formatted text [C++]
- _stprintf_p_l function
ms.assetid: a2ae78e8-6b0c-48d5-87a9-ea2365b0693d
ms.openlocfilehash: c55dce7d37d63c79e8c8d9976a76adf331412812
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579592"
---
# <a name="sprintfp-sprintfpl-swprintfp-swprintfpl"></a>_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l

Schreiben Sie formatierte Daten in eine Zeichenfolge mit der Möglichkeit, die Reihenfolge anzugeben, in der die Parameter in der Formatzeichenfolge verwendet werden.

## <a name="syntax"></a>Syntax

```C
int _sprintf_p(
   char *buffer,
   size_t sizeOfBuffer,
   const char *format [,
   argument_list]
);
int _sprintf_p_l(
   char *buffer,
   size_t sizeOfBuffer,
   const char *format,
   locale_t locale [,
   argument_list]
);
int _swprintf_p(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   const wchar_t *format [,
   argument_list]
);
int _swprintf_p_l(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   const wchar_t *format,
   locale_t locale [,
   argument_list]
);
```

### <a name="parameters"></a>Parameter

*buffer*<br/>
Speicherort für die Ausgabe

*sizeOfBuffer*<br/>
Die maximale Anzahl der zu speichernden Zeichen.

*format*<br/>
Formatsteuerzeichenfolge.

*argument_list*<br/>
Optionale Argumente, die Formatzeichenfolge.

*locale*<br/>
Das zu verwendende Gebietsschema.

Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Rückgabewert

Die Anzahl der geschriebenen Zeichen oder -1, wenn ein Fehler aufgetreten.

## <a name="remarks"></a>Hinweise

Die **_sprintf_p** -Funktion formatiert und speichert eine Reihe von Zeichen und Werten in *Puffer*. Jedes Argument in der *Argument_list* (sofern vorhanden) konvertiert und ausgegeben wird, entsprechend der jeweiligen Formatangabe in *Format*. Die *Format* Argument verwendet die [Syntax der Formatangabe für Printf und Wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md). Ein NULL-Zeichen wird nach dem letzten geschriebenen Zeichen angefügt. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert. Der Unterschied zwischen **_sprintf_p** und **Sprintf_s** ist, die **_sprintf_p** positionelle Parameter unterstützt, wodurch angeben der Reihenfolge, in denen die Argumente sind, in der Formatzeichenfolge verwendet. Weitere Informationen finden Sie unter [printf-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md).

**_swprintf_p** ist eine Breitzeichen-Version von **_sprintf_p**; die Zeigerargumente zu **_swprintf_p** sind Breitzeichen Zeichenfolgen. Erkennung von Codierungsfehlern in **_swprintf_p** möglicherweise nicht auf die in **_sprintf_p**. **_swprintf_p** und **Fwprintf_p** Verhalten sich identisch, außer dass **_swprintf_p** schreibt die Ausgabe in eine Zeichenfolge anstatt an ein Ziel vom Typ **Datei**, und **_swprintf_p** erfordert die *Anzahl* Parameter, um die maximale Anzahl zu schreibender Zeichen anzugeben. Die Versionen dieser Funktionen mit den **_l** -Suffix sind beinahe identisch, außer dass sie den übergebenen Gebietsschemaparameter anstelle des aktuellen threadgebietsschemas Locale-Parameter verwenden.

**_sprintf_p** gibt die Anzahl der Bytes in einem *Puffer*, das abschließende Null-Zeichen wird dabei nicht mitgezählt. **_swprintf_p** gibt die Anzahl der gespeicherten Breitzeichen *Puffer*, das beendende null-Breitzeichen wird dabei nicht mitgezählt. Wenn *Puffer* oder *Format* ein null-Zeiger ist oder wenn die Formatzeichenfolge ungültige Formatierungszeichen enthält, wird der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung ](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen-1 zurück und legen Sie **Errno** zu **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stprintf_p**|**_sprintf_p**|**_sprintf_p**|**_swprintf_p**|
|**_stprintf_p_l**|**_sprintf_p_l**|**_sprintf_p_l**|**_swprintf_p_l**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_sprintf_p**, **_sprintf_p_l**|\<stdio.h>|
|**_swprintf_p**, **_swprintf_p_l**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_sprintf_p.c
// This program uses _sprintf_p to format various
// data and place them in the string named buffer.
//

#include <stdio.h>

int main( void )
{
    char     buffer[200],
            s[] = "computer", c = 'l';
    int      i = 35,
            j;
    float    fp = 1.7320534f;

    // Format and print various data:
    j  = _sprintf_p( buffer, 200,
                     "   String:    %s\n", s );
    j += _sprintf_p( buffer + j, 200 - j,
                     "   Character: %c\n", c );
    j += _sprintf_p( buffer + j, 200 - j,
                     "   Integer:   %d\n", i );
    j += _sprintf_p( buffer + j, 200 - j,
                     "   Real:      %f\n", fp );

    printf( "Output:\n%s\ncharacter count = %d\n",
            buffer, j );
}
```

```Output
Output:
   String:    computer
   Character: l
   Integer:   35
   Real:      1.732053

character count = 79
```

## <a name="example"></a>Beispiel

```C
// crt_swprintf_p.c
// This is the wide character example which
// also demonstrates _swprintf_p returning
// error code.
#include <stdio.h>

#define BUFFER_SIZE 100

int main( void )
{
    wchar_t buffer[BUFFER_SIZE];
    int     len;

    len = _swprintf_p(buffer, BUFFER_SIZE, L"%2$s %1$d",
                      0, L" marbles in your head.");
    _printf_p( "Wrote %d characters\n", len );

    // _swprintf_p fails because string contains WEOF (\xffff)
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%s",
                      L"Hello\xffff world" );
    _printf_p( "Wrote %d characters\n", len );
}
```

```Output
Wrote 24 characters
Wrote -1 characters
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)<br/>
[vprintf-Funktionen](../../c-runtime-library/vprintf-functions.md)<br/>
[printf_p-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
