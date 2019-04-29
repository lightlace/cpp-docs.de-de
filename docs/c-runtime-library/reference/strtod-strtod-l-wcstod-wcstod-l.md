---
title: strtod, _strtod_l, wcstod, _wcstod_l
ms.date: 10/20/2017
apiname:
- wcstod
- _wcstod_l
- _strtod_l
- strtod
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcstod
- strtod
- wcstod
- _strtod_l
- _wcstod_l
- stdlib/strtod
- corecrt_wstdlib/wcstod
- stdlib/_strtod_l
- corecrt_wstdlib/_wcstod_l
helpviewer_keywords:
- wcstod_l function
- tcstod_l function
- _tcstod_l function
- strtod function
- _wcstod_l function
- wcstod function
- strtod_l function
- tcstod function
- _tcstod function
- _strtod_l function
- string conversion, to floating point values
ms.assetid: 0444f74a-ba2a-4973-b7f0-1d77ba88c6ed
ms.openlocfilehash: c8c2b3b491e2e7265829fa88580529dc757ace8c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376470"
---
# <a name="strtod-strtodl-wcstod-wcstodl"></a>strtod, _strtod_l, wcstod, _wcstod_l

Konvertieren von Zeichenfolgen in einen Wert mit doppelter Genauigkeit

## <a name="syntax"></a>Syntax

```C
double strtod(
   const char *strSource,
   char **endptr
);
double _strtod_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
double wcstod(
   const wchar_t *strSource,
   wchar_t **endptr
);
double wcstod_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*strSource*<br/>
Zu konvertierende mit NULL endende Zeichenfolge.

*endptr*<br/>
Zeiger auf ein Zeichen, mit dem die Überprüfung beendet wird.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**Strtod** gibt den Wert der Gleitkommazahl, außer wenn die Darstellung würde einen Überlauf, verursachen in dem Fall wird die Funktion zurückgegeben werden, +/-**HUGE_VAL**. Das Vorzeichen des **HUGE_VAL** entspricht dem Zeichen des Werts, der nicht dargestellt werden kann. **Strtod** gibt 0 zurück, wenn keine Konvertierung ausgeführt werden kann oder ein Unterlauf auftritt.

**Wcstod** gibt Werte analog zu **Strtod**. Für beide Funktionen **Errno** nastaven NA hodnotu **ERANGE** Überlauf oder Unterlauf auftritt und der Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Jede Funktion wandelt die Eingabezeichenfolge *StrSource* zu einem **doppelte**. Die **Strtod** -Funktion konvertiert *StrSource* auf einen Wert mit doppelter Genauigkeit. **Strtod** stoppt das Lesen der Zeichenfolge *StrSource* mit dem ersten Zeichen, die nicht als Teil einer Zahl erkannt. Dies ist möglicherweise das beendende NULL-Zeichen. **Wcstod** ist eine Breitzeichen-Version von **Strtod**, dessen *StrSource* Argument ist eine Breitzeichen-Zeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

Die **LC_NUMERIC** -kategorieeinstellung des aktuellen Gebietsschemas bestimmt das Erkennen des Basiszeichens in Punkt *StrSource*. Weitere Informationen finden Sie unter [setlocale](setlocale-wsetlocale.md). Die Funktionen ohne das **_l** -Suffix verwenden das aktuelle Gebietsschema. **_strtod_l** ist identisch mit **_strtod_l** , allerdings verwenden das *Gebietsschema* stattdessen den übergebenen. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Wenn *Endptr* nicht **NULL**, ein Zeiger auf das Zeichen, die Überprüfung beendet, wird gespeichert, an der Position zeigt *Endptr*. Wenn keine Konvertierung ausgeführt werden kann (keine gültigen Ziffern gefunden oder ungültige Basis angegeben) den Wert der *StrSource* befindet sich in den Speicherort verweist *Endptr*.

**Strtod** erwartet *StrSource* , zeigen Sie auf eine Zeichenfolge von einem der folgenden Formate:

[*Leerzeichen*] [*anmelden*] {*Ziffern* [*Basis* *Ziffern*] &#124;  *Basis* *Ziffern*} [{**e** &#124; **E**} [*anmelden*] *Ziffern*] [*Leerzeichen*] [*anmelden*] {**0 X** &#124; **0 X**} {*Hexdigits* [ *Basis* *Hexdigits*] &#124; *Basis* *Hexdigits*} [{**p** &#124; **P**} [*anmelden*] *Hexdigits*] [*Leerzeichen*] [*anmelden*] {} **INF** &#124; **UNENDLICH**} [*Leerzeichen*] [*anmelden*]  **NAN** [*Sequenz*]

Das optionale führende *Leerzeichen* besteht möglicherweise aus Leerzeichen und Tabulatorzeichen, die ignoriert werden; *anmelden* ist entweder Pluszeichen (+) oder Minuszeichen (-); *Ziffern* sind eine oder mehrere Dezimalstellen sind; *Hexdigits* sind einer oder mehreren hexadezimale Ziffern; *Basis* ist der Punkt Basiszeichens, entweder einen Punkt (.) im Gebietsschema "C" Standard oder die Gebietsschema-spezifische-Wert, wenn das aktuelle Gebietsschema unterscheidet, oder wenn *Gebietsschema* angegeben ist; eine *Sequenz* ist eine Sequenz von alphanumerischen Zeichen oder Unterstriche. In dezimalen und hexadezimalen Number Forms Wenn keine Ziffern vor dem Basiszeichen Punkt angezeigt werden muss mindestens eine nach dem Punkt Basiszeichen angezeigt. Im Dezimalformat, die Dezimalstellen können ein Exponent folgen, besteht aus einem einführenden Buchstaben (**e** oder **E**) und einer optional Zahl mit Vorzeichen. In hexadezimaler Form, die Hexadezimalziffern gefolgt werden ein Exponent, der besteht aus einem einführenden Buchstaben (**p** oder **P**) und eine Zahl mit optionalem Vorzeichen hexadezimale darstellt, die die der Exponent als Potenz von 2. In einer der Formen Wenn weder ein exponententeil noch ein Punkt Basiszeichen angezeigt wird, wird ein Punkt Basiszeichen angenommen, dass die letzte Ziffer in der Zeichenfolge folgen. Groß-/Kleinschreibung wird ignoriert, sowohl die **INF** und **NAN** Forms. Das erste Zeichen, das nicht mit einer der folgenden Formen passt beendet die Überprüfung.

Die UCRT-Versionen dieser Funktionen unterstützen keine Konvertierung von Fortran-Stil (**d** oder **D**) Buchstaben in Exponenten. Diese nicht-standardmäßige Erweiterung wurde in früheren Versionen der CRT unterstützt. Sie ist möglicherweise eine fehlerhafte Änderung für Ihren Code. Die UCRT-Versionen unterstützen Hexadezimalzeichenfolgen und Roundtripping für INF und NAN-Werte, die in früheren Versionen nicht unterstützt wurden. Dies kann auch wichtige Änderungen in Ihrem Code führen. Beispielsweise würde die Zeichenfolge "0x1a" interpretiert werden, von **Strtod** als 0,0 in früheren Versionen, sondern als 26.0 in der UCRT-Version.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**strtod**, **_strtod_l**|C: &lt;stdlib.h> C++: &lt;cstdlib> oder &lt;stdlib.h> |
|**wcstod**, **_wcstod_l**|C: &lt;stdlib.h> oder &lt;wchar.h> C++: &lt;cstdlib>, &lt;stdlib.h> oder &lt;wchar.h> |

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_strtod.c
// This program uses strtod to convert a
// string to a double-precision value; strtol to
// convert a string to long integer values; and strtoul
// to convert a string to unsigned long-integer values.
//

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char   *string, *stopstring;
   double x;
   long   l;
   int    base;
   unsigned long ul;

   string = "3.1415926This stopped it";
   x = strtod( string, &stopstring );
   printf( "string = %s\n", string );
   printf("   strtod = %f\n", x );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "-10110134932This stopped it";
   l = strtol( string, &stopstring, 10 );
   printf( "string = %s\n", string );
   printf("   strtol = %ld\n", l );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "10110134932";
   printf( "string = %s\n", string );

   // Convert string using base 2, 4, and 8:
   for( base = 2; base <= 8; base *= 2 )
   {
      // Convert the string:
      ul = strtoul( string, &stopstring, base );
      printf( "   strtol = %ld (base %d)\n", ul, base );
      printf( "   Stopped scan at: %s\n", stopstring );
   }
}
```

```Output
string = 3.1415926This stopped it
   strtod = 3.141593
   Stopped scan at: This stopped it

string = -10110134932This stopped it
   strtol = -2147483648
   Stopped scan at: This stopped it

string = 10110134932
   strtol = 45 (base 2)
   Stopped scan at: 34932
   strtol = 4423 (base 4)
   Stopped scan at: 4932
   strtol = 2134108 (base 8)
   Stopped scan at: 932
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
