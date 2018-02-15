---
title: strtod, _strtod_l, wcstod, _wcstod_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 10/20/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe18737b52ba2b04e3ee09813c6b48b6ebdf0363
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="strtod-strtodl-wcstod-wcstodl"></a>strtod, _strtod_l, wcstod, _wcstod_l

Konvertieren von Zeichenfolgen in einen Wert mit doppelter Genauigkeit

## <a name="syntax"></a>Syntax

```C
double strtod(
   const char *nptr,
   char **endptr
);
double _strtod_l(
   const char *nptr,
   char **endptr,
   _locale_t locale
);
double wcstod(
   const wchar_t *nptr,
   wchar_t **endptr
);
double wcstod_l(
   const wchar_t *nptr,
   wchar_t **endptr,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*nptr*  
Zu konvertierende mit NULL endende Zeichenfolge.

*endptr*  
Zeiger auf ein Zeichen, mit dem die Überprüfung beendet wird.

*locale*  
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

`strtod` Gibt den Wert der Gleitkommazahl, außer wenn die Darstellung einen Überlauf verursachen würde in dem Fall wird die Funktion zurückgegeben werden +/-`HUGE_VAL`. Das Zeichen von `HUGE_VAL` entspricht dem Zeichen des Werts, der nicht angezeigt werden kann. `strtod` gibt 0 zurück, wenn keine Konvertierung ausgeführt werden kann oder ein Unterlauf auftritt.

`wcstod` gibt Werte analog zu `strtod` zurück. `errno` wird für beide Funktionen auf `ERANGE` gesetzt, wenn ein Überlauf oder ein Unterlauf auftritt, und der Handler für ungültige Parameter wird aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Jede Funktion wandelt die Eingabezeichenfolge *Nptr* zu einem `double`. Die `strtod` -Funktion konvertiert *Nptr* auf einen Wert mit doppelter Genauigkeit. `strtod` Stoppt das Lesen der Zeichenfolge *Nptr* am ersten Zeichen, das nicht als Teil einer Zahl erkannt. Dies ist möglicherweise das beendende NULL-Zeichen. `wcstod` ist eine Breitzeichen-Version von `strtod`; die *Nptr* -Argument ist eine Breitzeichen-Zeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcstod`|`strtod`|`strtod`|`wcstod`|
|`_tcstod_l`|`_strtod_l`|`_strtod_l`|`_wcstod_l`|

Die `LC_NUMERIC` -kategorieneinstellung des aktuellen Gebietsschemas bestimmt erkennen des Basiszeichens in Punkt *Nptr*. Weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Funktionen ohne das `_l` -Suffix verwenden das aktuelle Gebietsschema. `_strtod_l` ist identisch mit `_strtod_l` , verwenden jedoch den *Gebietsschema* übergebene. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Wenn *Endptr* nicht `NULL`, ein Zeiger auf das Zeichen, die Überprüfung beendet, wird gespeichert, an der Speicherstelle *Endptr*. Wenn keine Konvertierung ausgeführt werden kann (keine gültigen Ziffern gefunden oder ungültige Basis angegeben wurde), den Wert der *Nptr* an der Speicherstelle gespeichert *Endptr*.

`strtod` erwartet *Nptr* , zeigen Sie auf eine Zeichenfolge mit einem der folgenden Formate:

[*Leerzeichen*] [*Anmeldung*] {*Ziffern* [*Basis* *Ziffern*] &#124; *Basis* *Ziffern*} [{**e** &#124; **E**} [*Anmeldung*] *Ziffern*]  
[*Leerzeichen*] [*Anmeldung*] {**0 X** &#124; **0 X**} {*Hexdigits* [*Basis* *Hexdigits*] &#124; *Basis* *Hexdigits*} [{**p** &#124; **P**} [*Anmeldung*] *Hexdigits*]  
[*Leerzeichen*] [*Anmeldung*] {**INF** &#124; **UNENDLICH**}  
[*whitespace*] [*sign*] **NAN** [*sequence*]

Das optionale führende *Leerzeichen* besteht möglicherweise aus Leerzeichen und Tabulatorzeichen, die ignoriert werden. *Anmeldung* ist entweder Pluszeichen (+) oder Minuszeichen (-) *Ziffern* sind mindestens eine Dezimalstelle; *Hexdigits* sind eine oder mehrere hexadezimale Ziffern; *Basis* ist der Punkt Basiszeichens, entweder einen Punkt (.) im Gebietsschema "C" "Standard" oder die Gebietsschema-spezifische Wert, wenn das aktuelle Gebietsschema unterschiedlich ist, oder wenn *Gebietsschema* angegeben ist; ein *Sequenz* ist eine Sequenz von alphanumerischen Zeichen oder Unterstriche enthalten. In dezimaler und hexadezimaler bildet Wenn keine Ziffern vor dem Basiszeichen Punkt stehen muss mindestens eine nach dem Punkt Basiszeichen stehen. Das Dezimalformat Dezimalstellen können werden ein Exponent folgen, besteht aus einem einführenden Buchstaben (**e** oder **E**) und einer optional Zahl mit Vorzeichen. In im hexadezimalen Format die Hexadezimalzeichen können werden ein Exponent folgen, besteht aus einem einführenden Buchstaben (**p** oder **P**) und optional mit Vorzeichen ganze Hexadezimalzahl darstellt, die die der Exponent als Potenz von 2. In einer der Formen Wenn weder ein exponententeil noch ein Punkt Basiszeichen angezeigt wird, wird ein Punkt Basiszeichen angenommen, dass die letzte Ziffer in der Zeichenfolge folgt. Groß-/Kleinschreibung wird ignoriert, sowohl die **INF** und **"NaN"** Forms. Das erste Zeichen, das nicht mit einer der folgenden Formen passt beendet die Überprüfung.

Die UCRT Versionen dieser Funktionen unterstützen keine Konvertierung von Fortran-Format (**d** oder **D**) Exponent Buchstaben. Diese nicht-standardmäßige Erweiterung wurde in früheren Versionen der CRT unterstützt. Sie ist möglicherweise eine fehlerhafte Änderung für Ihren Code. Die UCRT Versionen unterstützen Hexadezimalzeichenfolgen und Round-Tripping "INF" und "NaN"-Werte, die in früheren Versionen nicht unterstützt wurden. Dies kann auch wichtige Änderungen im Code verursachen. Beispielsweise würde die Zeichenfolge "0x1a" interpretiert werden, durch `strtod` als 0,0 in früheren Versionen, sondern als 26.0 in der UCRT-Version.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`strtod`, `_strtod_l`|C: &lt;stdlib.h> C++: &lt;cstdlib> oder &lt;stdlib.h> |
|`wcstod`, `_wcstod_l`|C: &lt;stdlib.h> oder &lt;wchar.h> C++: &lt;cstdlib>, &lt;stdlib.h> oder &lt;wchar.h> |

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

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
[Floating-Point Support (Gleitkommaunterstützung)](../../c-runtime-library/floating-point-support.md)   
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
[Gebietsschema](../../c-runtime-library/locale.md)   
[Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte](../../c-runtime-library/string-to-numeric-value-functions.md)   
[strtol, wcstol, _strtol_l, _wcstol_l](../../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)   
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](../../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)   
[atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
[localeconv](../../c-runtime-library/reference/localeconv.md)   
[_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
[_free_locale](../../c-runtime-library/reference/free-locale.md)