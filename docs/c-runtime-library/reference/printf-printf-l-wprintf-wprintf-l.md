---
title: printf, _printf_l, wprintf, _wprintf_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _printf_l
- wprintf
- _wprintf_l
- printf
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
- printf
- _tprintf
- wprintf
dev_langs:
- C++
helpviewer_keywords:
- printf function
- printf_l function
- tprintf_l function
- tprintf function
- _printf_l function
- wprintf function
- writing to console
- wprintf_l function
- _tprintf_l function
- _wprintf_l function
- _tprintf function
- printf function, format specification fields
- printf function, using
- formatted text [C++]
ms.assetid: 77a854ae-5b48-4865-89f4-f2dc5cf80f52
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e66c185a6ee56e4a82a98e62d8d2c7d8167399e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405236"
---
# <a name="printf-printfl-wprintf-wprintfl"></a>printf, _printf_l, wprintf, _wprintf_l

Druckt eine formatierte Ausgabe an den Standardausgabestream. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](printf-s-printf-s-l-wprintf-s-wprintf-s-l.md).

## <a name="syntax"></a>Syntax

```C
int printf(
   const char *format [,
   argument]...
);
int _printf_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int wprintf(
   const wchar_t *format [,
   argument]...
);
int _wprintf_l(
   const wchar_t *format,
   locale_t locale [,
   argument]...
);
```

### <a name="parameters"></a>Parameter

*format*<br/>
Formatsteuerung

*Argument*<br/>
Optionale Argumente.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Gibt die Anzahl gedruckter Zeichen oder einen negativen Wert zurück, wenn ein Fehler auftritt. Wenn *Format* ist **NULL**, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt die Funktion-1 zurück und legt **Errno** auf **EINVAL**. Wenn **EOF** (0xFFFF) in festgestellt wird *Argument*, gibt die Funktion-1 zurück.

Informationen zu **Errno** und andere Fehlercodes finden Sie unter [_doserrno, Errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Printf** -Funktion formatiert und druckt eine Reihe von Zeichen und Werten für den Standardausgabestream **"stdout"**. Wenn Argumente der *Format* Zeichenfolge, die *Format* Zeichenfolge muss Spezifikationen enthalten, die das Ausgabeformat für die Argumente bestimmen. **Printf** und [Fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md) Verhalten sich identisch, außer dass **Printf** schreibt die Ausgabe an **"stdout"** anstelle eines Ziels vom Typ **Datei** .

**"wprintf"** ist eine Breitzeichen-Version von **Printf**; *Format* ist eine Breitzeichen-Zeichenfolge. **"wprintf"** und **Printf** Verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **Printf** unterstützt derzeit keine Ausgabe in einen Unicode-Stream.

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter, der übergebenen Gebietsschemaparameter anstelle des aktuellen threadgebietsschemas.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_unicode definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tprintf**|**printf**|**printf**|**wprintf**|

Die *Format* Argument besteht aus normalen Zeichen, Escapesequenzen und (wenn Argumente folgen *Format*) Formatangaben. Die normalen Zeichen und die Escapesequenzen werden in kopiert **"stdout"** in Reihenfolge ihrer Darstellung. Zum Beispiel die Zeile:

```C
printf("Line one\n\t\tLine two\n");
```

erzeugt die Ausgabe:

```Output
Line one
        Line two
```

[Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) beginnen immer mit einem Prozentzeichen (**%**) und werden von links nach rechts gelesen. Wenn **Printf** die erste Formatspezifikation (falls vorhanden) trifft er konvertiert den Wert des ersten Arguments *Format* und gibt ihn entsprechend. Mit der zweiten Formatspezifikation wird das zweite Argument konvertiert und ausgegeben, usw. Wenn es mehrere Argumente als Formatspezifikationen gibt, werden die zusätzlichen Argumente ignoriert. Die Ergebnisse sind nicht definiert, wenn nicht genügend Argumente für alle Formatspezifikationen vorhanden sind.

> [!IMPORTANT]
> Stellen Sie sicher, dass *format* keine benutzerdefinierte Zeichenfolge ist.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tprintf**|**printf**|**printf**|**wprintf**|
|**_tprintf_l**|**_printf_l**|**_printf_l**|**_wprintf_l**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**Printf**, **_printf_l**|\<stdio.h>|
|**"wprintf"**, **_wprintf_l**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps der universellen Windows-Plattform (UWP) nicht unterstützt. Standardstream Handles, die mit der Konsole verknüpften sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in uwp-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_printf.c
// This program uses the printf and wprintf functions
// to produce formatted output.

#include <stdio.h>

int main( void )
{
   char     ch = 'h',
            *string = "computer";
   wchar_t  wch = L'w',
            *wstring = L"Unicode";
   int      count = -9234;
   double   fp = 251.7366;

   // Display integers
   printf( "Integer formats:\n"
           "   Decimal: %d  Justified: %.6d  "
           "Unsigned: %u\n",
           count, count, count, count );

   // Display decimals
   printf( "Decimal %d as:\n   Hex: %Xh  "
           "C hex: 0x%x  Octal: %o\n",
            count, count, count, count );

   // Display in different radixes
   printf( "Digits 10 equal:\n   Hex: %i  "
           "Octal: %i  Decimal: %i\n",
            0x10, 010, 10 );

   // Display characters
   printf("Characters in field (1):\n"
          "%10c%5hc%5C%5lc\n",
          ch, ch, wch, wch);
   wprintf(L"Characters in field (2):\n"
           L"%10C%5hc%5c%5lc\n",
           ch, ch, wch, wch);

   // Display strings
   printf("Strings in field (1):\n%25s\n"
          "%25.4hs\n   %S%25.3ls\n",
          string, string, wstring, wstring);
   wprintf(L"Strings in field (2):\n%25S\n"
           L"%25.4hs\n   %s%25.3ls\n",
           string, string, wstring, wstring);

   // Display real numbers
   printf("Real numbers:\n   %f %.2f %e %E\n",
          fp, fp, fp, fp );

   // Display pointer
   printf( "\nAddress as:   %p\n", &count);
}
```

### <a name="sample-output"></a>Beispielausgabe

```Output
Integer formats:
   Decimal: -9234  Justified: -009234  Unsigned: 4294958062
Decimal -9234 as:
   Hex: FFFFDBEEh  C hex: 0xffffdbee  Octal: 37777755756
Digits 10 equal:
   Hex: 16  Octal: 8  Decimal: 10
Characters in field (1):
         h    h    w    w
Characters in field (2):
         h    h    w    w
Strings in field (1):
                 computer
                     comp
   Unicode                      Uni
Strings in field (2):
                 computer
                     comp
   Unicode                      Uni
Real numbers:
   251.736600 251.74 2.517366e+002 2.517366E+002

Address as:   0012FF3C
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vprintf-Funktionen](../../c-runtime-library/vprintf-functions.md)<br/>
[_set_output_format](../../c-runtime-library/set-output-format.md)<br/>
