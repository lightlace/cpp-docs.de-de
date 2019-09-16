---
title: strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l
ms.date: 11/04/2016
api_name:
- wcstoimax
- _wcstoimax_l
- _strtoimax_l
- strtoimax
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
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wcstoimax
- _tcstoimax
- strtoimax
- _wcstoimax_l
- _strtoimax_l
- _tcstoimax_l
helpviewer_keywords:
- strtoimax funciton
- conversion functions
- _strtoimax_l function
- _wcstoimax_l function
- wcstoimax function
ms.assetid: 4530d3dc-aaac-4a76-b7cf-29ae3c98d0ae
ms.openlocfilehash: ea1ab72a361987d0ccdfe1f4b4a4efb6a0fb427e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957664"
---
# <a name="strtoimax-_strtoimax_l-wcstoimax-_wcstoimax_l"></a>strtoimax, _strtoimax_l, wcstoimax, _wcstoimax_l

Konvertiert eine Zeichenfolge in einen ganzzahligen Wert des größten unterstützten ganzzahligen Typs mit Vorzeichen.

## <a name="syntax"></a>Syntax

```C
intmax_t strtoimax(
   const char *strSource,
   char **endptr,
   int base
);
intmax_t wcstoimax(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
intmax_t _strtoimax_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
intmax_t _wcstoimax_l(
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
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

" **stringenmax** " gibt den Wert zurück, der in der Zeichenfolge " *darsource*" dargestellt wird, es sei denn, die Darstellung würde einen Überlauf verursachen – in diesem Fall gibt Sie **INTMAX_MAX** oder **INTMAX_MIN**zurück, und **errno** ist auf ERANGE festgelegt. Die Funktion gibt 0 zurück, wenn keine Konvertierung ausgeführt werden kann. **wcstoimax** gibt Werte analog zu " **straumax**" zurück.

**INTMAX_MAX** und **INTMAX_MIN** sind in stdint. h definiert.

Wenn " *strinsource* " **null** ist oder die *Basis* nicht NULL und entweder kleiner als 2 oder größer als 36 ist, wird **errno** auf **EINVAL**festgelegt.

Weitere Informationen zu diesen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die Funktion " **strinmax** " konvertiert " *stresource* " in eine **intmax_t**. Die breit Zeichen Version von " **straumax** " ist " **wcstoimax**;". Das *unsource* -Argument ist eine Zeichenfolge mit breit Zeichen. Ansonsten verhalten sich diese Funktionen identisch. Beide Funktionen enden das Lesen der Zeichenfolge " *Strauch* " beim ersten Zeichen, das nicht als Teil einer Zahl erkannt werden kann. Dies kann das abschließende Null-Zeichen sein, oder es kann das erste numerische Zeichen sein, das größer oder gleich der *Basis*ist.

Die **LC_NUMERIC** -Kategorieeinstellung des Gebiets Schemas bestimmt die Erkennung des Basis Zeichens in " *strinsource*". Weitere Informationen finden Sie unter [setlocale, _wsetlocale](setlocale-wsetlocale.md). Die Funktionen, die nicht über das **_l** -Suffix verfügen, verwenden das aktuelle Gebiets Schema. **_strtoimax_l** und **_wcstoimax_l** sind identisch mit den entsprechenden Funktionen, die nicht über das **_l** -Suffix verfügen, mit dem Unterschied, dass Sie stattdessen das übergebene Gebiets Schema verwenden. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Wenn *endptr* nicht **null**ist, wird ein Zeiger auf das Zeichen, das die Überprüfung beendet hat, an dem Speicherort gespeichert, auf den von *endptr*verwiesen wird. Wenn keine Konvertierung ausgeführt werden kann (keine gültigen Ziffern gefunden oder ungültige Basis angegeben), wird der Wert von " *strinsource* " an dem Speicherort gespeichert, auf den von *endptr*verwiesen wird.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoimax**|**strtoimax**|**strtoimax**|**wcstoimax**|
|**_tcstoimax_l**|**strtoimax_l**|**_strtoimax_l**|**_wcstoimax_l**|

" **Strauch Max** " erwartet, dass " *strinsource* " auf eine Zeichenfolge der folgenden Form verweist:

> [*Leerzeichen*] [{ **+** &#124; &#124; &#124; }] [0 [{x x}]] [Ziffern Buchstaben] **-**

Ein Leerraum kann aus *Leerzeichen und* Tabstopp Zeichen bestehen, die ignoriert werden. *Ziffern* sind eine oder mehrere Dezimalstellen. *Buchstaben* sind mindestens einer der Buchstaben "a" bis "z" (oder "a" bis "z"). Das erste Zeichen, das dieser Form nicht entspricht, beendet die Überprüfung. Wenn die *Basis* zwischen 2 und 36 ist, wird Sie als Basis der Zahl verwendet. Wenn *Base* den Wert 0 hat, werden die ersten Zeichen der Zeichenfolge, auf die von " *darsource* " verwiesen wird, zum Bestimmen der Basis verwendet. Wenn das erste Zeichen "0 " und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als oktale ganze Zahl interpretiert. Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als hexadezimale ganze Zahl interpretiert. Wenn das erste Zeichen "1" bis "9 " ist, wird die Zeichenfolge als ganze Dezimalzahl interpretiert. Den Buchstaben „a“ bis „z“ (bzw. „A“ bis „Z“) werden die Werten 10 bis 35 zugewiesen. Es sind nur Buchstaben zulässig, deren zugewiesene Werte kleiner als *base* sind. Das erste Zeichen außerhalb des Bereichs der Basis beendet die Überprüfung. Wenn die *Basis* beispielsweise 0 und das erste überprüfte Zeichen "0" ist, wird eine ganze Oktalzahl angenommen und ein "8"-oder "9"-Zeichen beendet die Überprüfung.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**strtoimax**, **_strtoimax_l**, **wcstoimax**, **_wcstoimax_l**|\<inttypes.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[strtoumax, _strtoumax_l, wcstoumax, _wcstoumax_l](strtoumax-strtoumax-l-wcstoumax-wcstoumax-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
