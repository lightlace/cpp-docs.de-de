---
title: remainder, remainderf, remainderl
ms.date: 04/05/2018
api_name:
- remainderl
- remainder
- remainderf
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
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- remainderf
- remainder
- remainderl
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
ms.openlocfilehash: 851f022325bb617cb2b0ae9a331b680b9d9fd303
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949425"
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl

Berechnet den Rest des Quotienten aus zwei Gleitkommawerten, gerundet auf den nächsten ganzzahligen Wert.

## <a name="syntax"></a>Syntax

```C
double remainder( double x, double y );
float remainderf( float x, float y );
long double remainderl( long double x, long double y );
```

```cpp
float remainder( float x, float y ); /* C++ only */
long double remainder( long double x, long double y ); /* C++ only */
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der Zähler.

*y*<br/>
Der Nenner.

## <a name="return-value"></a>Rückgabewert

Der Gleit Komma Rest von *x* / *y*. Wenn der Wert von *y* 0,0 ist, gibt **Rest** einen stillen NaN-Wert zurück. Informationen zur Darstellung eines stillen Nan durch die **printf** -Familie finden Sie unter [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Hinweise

Die **Rest** -Funktionen berechnen den Gleit Komma Rest *r* von *x* / *y* , sodass *x* = *n* \* *y* + *r*, wobei *n* die ganze Zahl, die dem Wert am nächsten liegt, bis zu *x* / *y* , und *n*ist auch immer, wenn &#124; *n* - *x* / *y* &#124; = 1/2 Wenn *r* = 0 ist, hat *r* das gleiche Vorzeichen wie *x*.

Da C++ das überladen zulässt, können Sie über Ladungen von **Restwerten** aufzurufen, die **float** -oder **Long** **Double** -Werte verwenden und zurückgeben. In einem C-Programm nimmt **Rest** immer zwei **doppelte** Argumente an und gibt einen **Double**-Wert zurück.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|--------------|---------------------|-|
|**remainder**, **remainderf**, **remainderl**|\<math.h>|\<cmath> oder \<math.h>|

Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_remainder.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = remainder(w, x);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
