---
title: printf_s, _printf_s_l, wprintf_s, _wprintf_s_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _printf_s_l
- wprintf_s
- _wprintf_s_l
- printf_s
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
- wprintf_s
- printf_s
dev_langs:
- C++
helpviewer_keywords:
- wprintf_s function
- tprintf_s function
- _tprintf_s function
- printf_s_l function
- printf_s function
- _printf_s_l function
- printf function, format specification fields
- printf function, using
- _tprintf_s_l function
- wprintf_s_l function
- formatted text [C++]
- tprintf_s_l function
- _wprintf_s_l function
ms.assetid: 044ebb2e-5cc1-445d-bb4c-f084b405615b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ffe17ed1fc562b61d306294e970a070b03186e7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405262"
---
# <a name="printfs-printfsl-wprintfs-wprintfsl"></a>printf_s, _printf_s_l, wprintf_s, _wprintf_s_l

Druckt eine formatierte Ausgabe an den Standardausgabestream. Diese Versionen von [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md) enthalten Sicherheitserweiterungen, wie unter [Sicherheitserweiterungen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
int printf_s(
   const char *format [,
   argument]...
);
int _printf_s_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int wprintf_s(
   const wchar_t *format [,
   argument]...
);
int _wprintf_s_l(
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

Gibt die Anzahl gedruckter Zeichen oder einen negativen Wert zurück, wenn ein Fehler auftritt.

## <a name="remarks"></a>Hinweise

Die **Printf_s** -Funktion formatiert und druckt eine Reihe von Zeichen und Werten für den Standardausgabestream **"stdout"**. Wenn Argumente der *Format* Zeichenfolge, die *Format* Zeichenfolge muss Spezifikationen enthalten, die das Ausgabeformat für die Argumente bestimmen.

Der Hauptunterschied zwischen **Printf_s** und **Printf** handelt, **Printf_s** die Formatzeichenfolge auf gültige Formatierungszeichen überprüft wird, wohingegen **Printf**  überprüft nur, wenn die Formatzeichenfolge ein null-Zeiger ist. Wenn bei einer der beiden Überprüfungen ein Fehler auftritt, wird der ungültige Parameterhandler gerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md)beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt die Funktion-1 zurück und legt **Errno** auf **EINVAL**.

Informationen zu **Errno** und andere Fehlercodes finden Sie unter [_doserrno, Errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**Printf_s** und **Fprintf_s** Verhalten sich identisch, außer dass **Printf_s** schreibt die Ausgabe an **"stdout"** anstelle eines Ziels vom Typ **Datei**. Weitere Informationen finden Sie unter [fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md).

**Wprintf_s** ist eine Breitzeichen-Version von **Printf_s**; *Format* ist eine Breitzeichen-Zeichenfolge. **Wprintf_s** und **Printf_s** Verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **Printf_s** derzeit die Ausgabe in eine Unicode-Stream unterstützt keine.

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter, der übergebenen Gebietsschemaparameter anstelle des aktuellen threadgebietsschemas.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_unicode definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tprintf_s**|**printf_s**|**printf_s**|**wprintf_s**|
|**_tprintf_s_l**|**_printf_s_l**|**_printf_s_l**|**_wprintf_s_l**|

Die *Format* Argument besteht aus normalen Zeichen, Escapesequenzen und (wenn Argumente folgen *Format*) Formatangaben. Die normalen Zeichen und die Escapesequenzen werden in kopiert **"stdout"** in Reihenfolge ihrer Darstellung. Beispiel: Die Zeile

```C
printf_s("Line one\n\t\tLine two\n");
```

erzeugt die Ausgabe

```Output
Line one
        Line two
```

[Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) beginnen immer mit einem Prozentzeichen (**%**) und werden von links nach rechts gelesen. Wenn **Printf_s** die erste Formatspezifikation (falls vorhanden) trifft er konvertiert den Wert des ersten Arguments *Format* und gibt ihn entsprechend. Mit der zweiten Formatspezifikation wird das zweite Argument konvertiert und ausgegeben, usw. Wenn es mehrere Argumente als Formatspezifikationen gibt, werden die zusätzlichen Argumente ignoriert. Die Ergebnisse sind nicht definiert, wenn nicht genügend Argumente für alle Formatspezifikationen vorhanden sind.

> [!IMPORTANT]
> Stellen Sie sicher, dass *format* keine benutzerdefinierte Zeichenfolge ist.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**Printf_s**, **_printf_s_l**|\<stdio.h>|
|**Wprintf_s**, **_wprintf_s_l**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps der universellen Windows-Plattform (UWP) nicht unterstützt. Standardstream Handles, die mit der Konsole verknüpften sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in uwp-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_printf_s.c
/* This program uses the printf_s and wprintf_s functions
* to produce formatted output.
*/

#include <stdio.h>

int main( void )
{
   char   ch = 'h', *string = "computer";
   int    count = -9234;
   double fp = 251.7366;
   wchar_t wch = L'w', *wstring = L"Unicode";

   /* Display integers. */
   printf_s( "Integer formats:\n"
           "   Decimal: %d  Justified: %.6d  Unsigned: %u\n",
           count, count, count );

   printf_s( "Decimal %d as:\n   Hex: %Xh  C hex: 0x%x  Octal: %o\n",
            count, count, count, count );

   /* Display in different radixes. */
   printf_s( "Digits 10 equal:\n   Hex: %i  Octal: %i  Decimal: %i\n",
            0x10, 010, 10 );

   /* Display characters. */

   printf_s("Characters in field (1):\n%10c%5hc%5C%5lc\n", ch, ch, wch, wch);
   wprintf_s(L"Characters in field (2):\n%10C%5hc%5c%5lc\n", ch, ch, wch, wch);

   /* Display strings. */

   printf_s("Strings in field (1):\n%25s\n%25.4hs\n   %S%25.3ls\n",
   string, string, wstring, wstring);
   wprintf_s(L"Strings in field (2):\n%25S\n%25.4hs\n   %s%25.3ls\n",
       string, string, wstring, wstring);

   /* Display real numbers. */
   printf_s( "Real numbers:\n   %f %.2f %e %E\n", fp, fp, fp, fp );

   /* Display pointer. */
   printf_s( "\nAddress as:   %p\n", &count);

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

Address as:   0012FF78

```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vprintf-Funktionen](../../c-runtime-library/vprintf-functions.md)<br/>
