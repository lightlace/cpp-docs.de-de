---
title: strtol, wcstol, _strtol_l, _wcstol_l
ms.date: 01/14/2020
api_name:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
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
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
helpviewer_keywords:
- wcstol function
- wcstol_l function
- _tcstol function
- string conversion, to integers
- tcstol function
- strtol_l function
- _wcstol_l function
- _strtol_l function
- strtol function
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
no-loc:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
- LONG_MAX
- LONG_MIN
- errno
- ERANGE
- EINVAL
- LC_NUMERIC
- _tcstol
- _tcstol_l
- localeconv
- setlocale
- _wsetlocale
- strtod
- _strtod_l
- wcstod
- _wcstod_l
- strtoll
- _strtoll_l
- wcstoll
- _wcstoll_l
- strtoul
- _strtoul_l
- wcstoul
- _wcstoul_l
- atof
- _atof_l
- _wtof
- _wtof_l
ms.openlocfilehash: 83054e1b31b56fda96bdea198ab34d65d633f335
ms.sourcegitcommit: e93f3e6a110fe38bc642055bdf4785e620d4220f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76123928"
---
# <a name="opno-locstrtol-opno-locwcstol-opno-loc_strtol_l-opno-loc_wcstol_l"></a>strtol, wcstol, _strtol_l, _wcstol_l

Konvertiert Zeichen folgen in einen **langen** ganzzahligen Wert.

## <a name="syntax"></a>Syntax

```C
long strtol(
   const char *string,
   char **end_ptr,
   int base
);
long wcstol(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base
);
long _strtol_l(
   const char *string,
   char **end_ptr,
   int base,
   _locale_t locale
);
long _wcstol_l(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameters

*string*\
Zu konvertierende mit NULL endende Zeichenfolge.

*end_ptr*\
Ein Ausgabeparameter, der auf das Zeichen nach dem letzten interpretierten Zeichen zeigen soll. Ignoriert, wenn **null**.

*base*\
Zu verwendende Zahlenbasis.

Gebiets *Schema\*
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**strtol** , **wcstol** , **_strtol_l** und **_wcstol_l** geben den in der *Zeichenfolge*dargestellten Wert zurück. Wenn keine Konvertierung möglich ist, wird 0 zurückgegeben. Wenn die Darstellung einen Überlauf verursachen würde, geben Sie **LONG_MAX** oder **LONG_MIN** zurück.

**errno** ist auf **ERANGE** festgelegt, wenn ein Überlauf oder ein Unterlauf auftritt. Sie wird auf **EINVAL** festgelegt, wenn die *Zeichenfolge* **null**ist. Oder, wenn *Base* ungleich 0 (null) und kleiner als 2 oder größer als 36 ist. Weitere Informationen zu **ERANGE** , **EINVAL** und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die Funktionen **strtol** , **wcstol** , **_strtol_l** und **_wcstol_l** konvertieren *String* in **Long**. Sie beendet das Lesen der *Zeichenfolge* beim ersten Zeichen, das nicht als Teil einer Zahl erkannt wird. Dies kann das abschließende Null-Zeichen oder das erste alphanumerische Zeichen sein, das größer oder gleich der *Basis*ist.

**wcstol** und **_wcstol_l** sind breit Zeichen Versionen von **strtol** und **_strtol_l** . Das *Zeichen* folgen Argument ist eine Zeichenfolge mit breit Zeichen. Diese Funktionen Verhalten sich identisch mit **strtol** und **_strtol_l** andernfalls. Die **LC_NUMERIC** Kategorieeinstellung des Gebiets Schemas bestimmt die Erkennung des Basis Zeichens (der Bruch Komma-oder Dezimaltrennzeichen) in der *Zeichenfolge*. Die Funktionen **strtol** und **wcstol** das aktuelle Gebiets Schema verwenden. **_strtol_l** und **_wcstol_l** stattdessen das übergebene Gebiets Schema verwenden. Weitere Informationen finden Sie unter [setlocale[] und Gebiets](../../c-runtime-library/locale.md)Schema.

Wenn *end_ptr* **null**ist, wird es ignoriert. Andernfalls wird ein Zeiger auf das Zeichen, das die Überprüfung beendet hat, an dem Speicherort gespeichert, auf den von *end_ptr*verwiesen wird. Es ist keine Konvertierung möglich, wenn keine gültigen Ziffern gefunden werden oder eine ungültige Basis angegeben wird. Der Wert der *Zeichenfolge* wird dann an dem Speicherort gespeichert, auf den von *end_ptr*verwiesen wird.

**strtol** erwartet, dass die *Zeichen* Folge auf eine Zeichenfolge der folgenden Form verweist:

> [*Leerzeichen*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [*Alpha*numerische Zeichen]

Eckige Klammern (`[ ]`) umgeben optionale Elemente. Geschweifte Klammern und ein senkrechter Strich (`{ | }`) umschließen Alternativen für ein einzelnes Element. *Leerräume können aus* Leerzeichen und Tabstopp Zeichen bestehen, die ignoriert werden. *alphanumerische* Zeichen sind Dezimalstellen oder die Buchstaben "a" bis "z" (oder "a" bis "z"). Das erste Zeichen, das dieser Form nicht entspricht, beendet die Überprüfung. Wenn die *Basis* zwischen 2 und 36 ist, wird Sie als Basis der Zahl verwendet. Wenn *Base* den Wert 0 hat, werden die ersten Zeichen der Zeichenfolge, auf die von *String* verwiesen wird, verwendet, um die Basis zu bestimmen. Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "x" ist, wird die Zeichenfolge als oktale ganze Zahl interpretiert. Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als hexadezimale ganze Zahl interpretiert. Wenn das erste Zeichen "1" bis "9 " ist, wird die Zeichenfolge als ganze Dezimalzahl interpretiert. Den Buchstaben "a" bis "z" (oder "a" bis "z") werden die Werte 10 bis 35 zugewiesen. Der Scan lässt nur Buchstaben zu, deren Werte kleiner als *Base*sind. Das erste Zeichen außerhalb des Bereichs der Basis beendet die Überprüfung. Angenommen, die *Zeichenfolge* beginnt mit "01". Wenn *Base* 0 ist, geht der Scanner davon aus, dass es sich um eine oktale ganze Zahl handelt. Das Zeichen "8" oder "9" beendet die Überprüfung.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

## <a name="requirements"></a>-Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**strtol**|\<stdlib.h>|
|**wcstol**|\<stdlib.h> oder \<wchar.h>|
|**_strtol_l**|\<stdlib.h>|
|**_wcstol_l**|\<stdlib.h> oder \<wchar.h>|

Die Funktionen **_strtol_l** und **_wcstol_l** sind Microsoft-spezifisch, nicht Teil der Standard-C-Bibliothek. Zusätzliche Informationen zur Kompatibilität finden Sie unter [Compatibility](../compatibility.md).

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [strtod](strtod-strtod-l-wcstod-wcstod-l.md).

## <a name="see-also"></a>Siehe auch

[Daten Konvertierungs](../data-conversion.md)\
[Locale](../locale.md)\
[localeconv](localeconv.md)\
[setlocale_wsetlocale](setlocale-wsetlocale.md)\
[Funktionen für Zeichen folgen zu numerischen Werten](../string-to-numeric-value-functions.md)\
[strtod, _strtod_lwcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)\
[strtoll, _strtoll_lwcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)\
[strtoul, _strtoul_lwcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)\
[atof, _atof_l_wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)
