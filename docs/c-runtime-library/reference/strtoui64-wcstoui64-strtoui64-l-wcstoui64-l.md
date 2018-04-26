---
title: _strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _strtoui64
- _strtoui64_l
- _wcstoui64
- _wcstoui64_l
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
- _wcstoui64_l
- strtoui64_l
- wcstoui64
- _wcstoui64
- _strtoui64_l
- strtoui64
- _strtoui64
- wcstoui64_l
dev_langs:
- C++
helpviewer_keywords:
- _strtoui64_l function
- _wcstoui64_l function
- string conversion, to integers
- wcstoui64_l function
- _strtoui64 function
- _wcstoui64 function
- wcstoui64 function
- strtoui64_l function
- strtoui64 function
ms.assetid: 7fcb537e-4554-4ceb-a5b6-bc09244e72ef
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d596f66bd3272449466a080cf3ecd2f58fdd8627
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="strtoui64-wcstoui64-strtoui64l-wcstoui64l"></a>_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l

Konvertieren einer Zeichenfolge in einen nicht signierten **__int64** Wert.

## <a name="syntax"></a>Syntax

```C
unsigned __int64 _strtoui64(
   const char *strSource,
   char **endptr,
   int base
);
unsigned __int64 _wcstoui64(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
unsigned __int64 _strtoui64_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
unsigned __int64 _wcstoui64(
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
Zeiger auf ein Zeichen, mit dem die Überprüfung beendet wird.

*base*<br/>
Zu verwendende Zahlenbasis.

*locale*<br/>
Zu verwendendes Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**_strtoui64** gibt den Wert in der Zeichenfolge dargestellt zurück *StrSource*, außer wenn die Darstellung würde einen Überlauf verursachen, in denen gibt Fall **_UI64_MAX**. **_strtoui64** gibt 0 zurück, wenn keine Konvertierung ausgeführt werden kann.

**_UI64_MAX** in Grenzen definiert ist. H.

Wenn *StrSource* ist **NULL** oder *Basis* ungleich NULL ist und entweder weniger als 2 oder größer als 36 **Errno** festgelegt ist, um **EINVAL** .

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_strtoui64** -Funktion konvertiert *StrSource* auf eine **ohne Vorzeichen** **__int64**. **_wcstoui64** ist eine Breitzeichen-Version von **_strtoui64**; die *StrSource* -Argument ist eine Breitzeichen-Zeichenfolge. Anderenfalls verhalten sich diese Funktionen identisch.

Beide Funktionen beenden das Lesen einer Zeichenfolge *StrSource* am ersten Zeichen, die nicht als Teil einer Zahl erkannt. Dies ist möglicherweise das abschließende Nullzeichen oder möglicherweise das erste numerische Zeichen größer als oder gleich *Basis*.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoui64**|**_strtoui64**|**_strtoui64**|**_wstrtoui64**|
|**_tcstoui64_l**|**_strtoui64_l**|**_strtoui64_l**|**_wstrtoui64_l**|

Des aktuellen Gebietsschemas **LC_NUMERIC** -kategorieneinstellung bestimmt erkennen des Basiszeichens in *StrSource*; Weitere Informationen finden Sie unter [Setlocale](setlocale-wsetlocale.md). Die Funktionen ohne das Suffix _l verwenden das aktuelle Gebietsschema; **_strtoui64_l** und **_wcstoui64_l** sind identisch mit den entsprechenden Funktionen ohne das **_l** suffix verwenden allerdings das übergebene Gebietsschema. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Wenn *Endptr* nicht **NULL**, ein Zeiger auf das Zeichen, die Überprüfung beendet, wird gespeichert, an der Speicherstelle *Endptr*. Wenn keine Konvertierung ausgeführt werden kann (keine gültigen Ziffern gefunden oder ungültige Basis angegeben wurde), den Wert der *StrSource* an der Speicherstelle gespeichert *Endptr*.

**_strtoui64** erwartet *StrSource* , zeigen Sie auf eine Zeichenfolge der folgenden Form:

> [*Leerzeichen*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*Ziffern* &#124; *Buchstaben*]  

Ein *Leerzeichen* besteht möglicherweise aus Leerzeichen und Tabulatorzeichen, die ignoriert werden. *Ziffern* sind eine oder mehrere Dezimalstellen. *Buchstaben* sind eine oder mehrere der Buchstaben "a" bis "Z" (oder "A" bis "Z"). Das erste Zeichen, das dieser Form nicht entspricht, beendet die Überprüfung. Wenn *Basis* ist zwischen 2 und 36 liegt, wird dieser Wert als Basis der Zahl verwendet wird. Wenn *Basis* ist 0, die ersten Zeichen der Zeichenfolge verweist *StrSource* werden zur Bestimmung der Basis verwendet. Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als ganze Oktalzahl interpretiert. Wenn das erste Zeichen "0" und das zweite Zeichen nicht "x" oder "X" ist, wird die Zeichenfolge als hexadezimale ganze Zahl interpretiert. Wenn das erste Zeichen "1" bis "9 " ist, wird die Zeichenfolge als ganze Dezimalzahl interpretiert. Den Buchstaben „a“ bis „z“ (bzw. „A“ bis „Z“) werden die Werten 10 bis 35 zugewiesen. Es sind nur Buchstaben zulässig, deren zugewiesene Werte kleiner als *base* sind. Das erste Zeichen außerhalb des Bereichs der Basis beendet die Überprüfung. Z. B. wenn *Basis* ist 0 und das erste überprüfte Zeichen "0", eine ganze Oktalzahl angenommen und ein "8" oder "9"-Zeichen beendet die Überprüfung.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_strtoui64**|\<stdlib.h>|
|**_wcstoui64**|\<stdlib.h> oder \<wchar.h>|
|**_strtoui64_l**|\<stdlib.h>|
|**_wcstoui64_l**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_strtoui64.c
#include <stdio.h>

unsigned __int64 atoui64(const char *szUnsignedInt) {
   return _strtoui64(szUnsignedInt, NULL, 10);
}

int main() {
   unsigned __int64 u = atoui64("18446744073709551615");
   printf( "u = %I64u\n", u );
}
```

```Output
u = 18446744073709551615
```

## <a name="see-also"></a>Siehe auch

[Datenkonvertierung](../../c-runtime-library/data-conversion.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Funktionen zur Konvertierung von Zeichenfolgen in numerische Werte](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
