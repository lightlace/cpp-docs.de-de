---
title: strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l
ms.date: 11/04/2016
apiname:
- _wcstoumax_l
- _strtoumax_l
- wcstoumax
- strtoumax
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
- wcstoumax
- _tcstoumax
- _strtoumax_l
- _wcstoumax_l
- _tcstoumax_l
- strtoumax
helpviewer_keywords:
- _strtoumax_l function
- conversion functions
- wcstoumax function
- _wcstoumax_l function
- strtoumax function
ms.assetid: 566769f9-495b-4508-b9c6-02217a578897
ms.openlocfilehash: c9c8ca79ed68b23586d9fef979bc8d47b72ca846
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62379167"
---
# <a name="strtoumax-strtoumaxl-wcstoumax-wcstoumaxl"></a>strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l

Konvertiert Zeichenfolgen in einen ganzzahligen Wert des größten unterstützten ganzzahligen Typs ohne Vorzeichen.

## <a name="syntax"></a>Syntax

```C
uintmax_t strtoumax(
   const char *strSource,
   char **endptr,
   int base
);
uintmax_t _strtoumax_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
uintmax_t wcstoumax(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
uintmax_t _wcstoumax_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*strSource*<br/>
Zu konvertierende mit NULL endende Zeichenfolge.

*endptr*<br/>
Zeiger auf das Zeichen, das die Überprüfung stoppt.

*base*<br/>
Zu verwendende Zahlenbasis.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**Strtoumax** gibt den konvertierten Wert zurück, sofern vorhanden, oder **UINTMAX_MAX** bei einem Überlauf. **Strtoumax** gibt 0 zurück, wenn keine Konvertierung ausgeführt werden kann. **Wcstoumax** gibt Werte analog zu **Strtoumax**. Für beide Funktionen **Errno** nastaven NA hodnotu **ERANGE** Wenn Überlauf oder Unterlauf auftritt.

Weitere Informationen zu diesen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen konvertiert die Eingabezeichenfolge *StrSource* zu einem **Uintmax_t** Integer-Wert.

**Strtoumax** stoppt das Lesen der Zeichenfolge *StrSource* mit dem ersten Zeichen, die nicht als Teil einer Zahl erkannt. Dies ist möglicherweise das abschließende Nullzeichen, oder es ist das erste numerische Zeichen, die größer als oder gleich ist *Basis*. Die **LC_NUMERIC** -kategorieeinstellung des Gebietsschemas bestimmt das Erkennen des Basiszeichens in *StrSource*. Weitere Informationen finden Sie unter [setlocale, _wsetlocale](setlocale-wsetlocale.md). **Strtoumax** und **Wcstoumax** verwenden das aktuelle Gebietsschema. **_strtoumax_l** und **_wcstoumax_l** sind identisch, verwenden jedoch stattdessen das Gebietsschema, das übergeben wird. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Wenn *Endptr* nicht **NULL**, ein Zeiger auf das Zeichen, die Überprüfung beendet, wird gespeichert, an dem Speicherort, auf das von *Endptr*. Wenn keine Konvertierung ausgeführt werden kann (keine gültigen Ziffern gefunden oder ungültige Basis angegeben) den Wert der *StrSource* wird an dem Speicherort gespeichert, auf das von *Endptr*.

Die Breitzeichen-Version des **Strtoumax** ist **Wcstoumax**, dessen *StrSource* Argument ist eine Breitzeichen-Zeichenfolge. Ansonsten verhalten sich diese Funktionen identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoumax**|**strtoumax**|**strtoumax**|**wcstoumax**|
|**_tcstoumax_l**|**strtoumax_l**|**_strtoumax_l**|**_wcstoumax_l**|

**Strtoumax** erwartet *StrSource* auf eine Zeichenfolge der folgenden Form zeigt:

> [*Leerzeichen*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*Ziffern* &#124; *Buchstaben*]  

Ein *Leerzeichen* besteht möglicherweise aus Leerzeichen und Tabulatorzeichen, die ignoriert werden. *Ziffern* sind eine oder mehrere Dezimalstellen. *Buchstaben* können eine oder mehrere der Buchstaben "a" bis "Z" (oder "A" bis "Z"). Das erste Zeichen, das dieser Form nicht entspricht, beendet die Überprüfung. Wenn *Basis* zwischen 2 und 36 liegt, ist er als der Basis der Zahl verwendet wird. Wenn *Basis* ist 0, die ersten Zeichen der Zeichenfolge, auf das von *StrSource* werden verwendet, um die Basis festzulegen. Wenn das erste Zeichen "0 " und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als oktale ganze Zahl interpretiert. Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als hexadezimale ganze Zahl interpretiert. Wenn das erste Zeichen "1" bis "9 " ist, wird die Zeichenfolge als ganze Dezimalzahl interpretiert. Den Buchstaben „a“ bis „z“ (bzw. „A“ bis „Z“) werden die Werten 10 bis 35 zugewiesen. Es sind nur Buchstaben zulässig, deren zugewiesene Werte kleiner als *base* sind. Das erste Zeichen außerhalb des Bereichs der Basis beendet die Überprüfung. Z. B. wenn *Basis* ist 0 und das erste überprüfte Zeichen "0", eine ganze Oktalzahl angenommen und ein "8" oder "9"-Zeichen beendet die Überprüfung. **Strtoumax** lässt ein Pluszeichen (**+**) oder Minuszeichen (-) (**-**) Präfix; ein führendes Minuszeichen gibt an, dass der Rückgabewert das Zweierkomplement des ist der Absolute-Wert, der die konvertierte Zeichenfolge.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**strtoumax**|\<stdlib.h>|
|**wcstoumax**|\<stdlib.h> oder \<wchar.h>|
|**_strtoumax_l**|\<stdlib.h>|
|**_wcstoumax_l**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [strtod](strtod-strtod-l-wcstod-wcstod-l.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l](strtoimax-strtoimax-l-wcstoimax-wcstoimax-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
