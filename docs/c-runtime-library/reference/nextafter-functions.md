---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
ms.date: 04/05/2018
api_name:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
- nextafter
- _nextafter
- nextafterf
- nextafterl
- _nextafterf
- math/nextafter
- math/nextafterf
- math/nextafterl
- nexttoward
- nexttowardf
- nexttowardl
- math/nexttoward
- math/nexttowardf
- math/nexttowardl
helpviewer_keywords:
- _nextafter function
- nextafter function
- _nextafterf function
- nextafterf function
- nextafterl function
- nexttoward function
- nexttowardf function
- nexttowardl function
ms.assetid: 9785bfb9-de53-4bd0-9637-f05fa0c1f6ab
ms.openlocfilehash: c56c9f8032c9af2ed4404428abe3b9ee26b4b603
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951357"
---
# <a name="nextafter-nextafterf-nextafterl-_nextafter-_nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl

Gibt den nächsten darstellbaren Gleitkommawert zurück.

## <a name="syntax"></a>Syntax

```C
double nextafter( double x, double y );
float nextafterf( float x, float y );
long double nextafterl( long double x, long double y );

double _nextafter( double x, double y );
float _nextafterf( float x, float y ); /* x64 only */

double nexttoward( double x, long double y );
float nexttowardf( float x, long double y );
long double nexttowardl( long double x, long double y );
```

```cpp
float nextafter( float x, float y ); /* C++ only, requires <cmath> */
long double nextafter( long double x, long double y ); /* C++ only, requires <cmath> */

float nexttoward( float x, long double y ); /* C++ only, requires <cmath> */
long double nexttoward( long double x, long double y ); /* C++ only, requires <cmath> */
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der Gleitkommawert, der den Startpunkt markiert.

*y*<br/>
Der Gleitkommawert, der den Zielpunkt markiert.

## <a name="return-value"></a>Rückgabewert

Gibt den nächsten darstellbaren Gleit Komma Wert des Rückgabe Typs nach *x* in der Richtung *y*zurück. Wenn *x* und *y* gleich sind, gibt die Funktion *y*in den Rückgabetyp konvertiert zurück, ohne dass eine Ausnahme ausgelöst wird. Wenn *x* nicht gleich *y*ist und das Ergebnis ein DENORMAL oder NULL ist, werden die Gleit Komma-Ausnahmezustände **FE_UNDERFLOW** und **FE_INEXACT** festgelegt, und das korrekte Ergebnis wird zurückgegeben. Wenn " *x* " oder " *y* " ein NaN-Wert ist, ist der Rückgabewert einer der Eingabe-Nans. Wenn *x* begrenzt ist und das Ergebnis unendlich oder nicht im Typ darstellbar ist, wird eine ordnungsgemäß signierte unendlich oder NaN zurückgegeben, die **FE_OVERFLOW** -und **FE_INEXACT** -Gleit Komma Ausnahmezustände werden festgelegt, und **errno** ist auf ERANGE festgelegt.

## <a name="remarks"></a>Hinweise

Die **nextafter** -und **NexTTo** -Funktions Familien sind äquivalent, außer dem Parametertyp *y*. Wenn *x* und *y* gleich sind, wird der zurückgegebene Wert *y* in den Rückgabetyp konvertiert.

Da C++ das überladen zulässt, können Sie \<, wenn Sie cmath-> einschließen, über Ladungen von **nextafter** und **NexTTo** aufzurufen, die **float** -und **Long** **Double** -Typen zurückgeben. In einem C-Programm geben **nextafter** und **NexTTo** immer **Double**zurück.

Die Funktionen **_nextafter** und **_nextafterf** sind Microsoft-spezifisch. Die **_nextafterf** -Funktion ist nur verfügbar, wenn für x64 kompiliert wird.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**, **nextafterf**, **nextafterl**, **_nextafterf**, **nexttoward**, **nexttowardf**, **nexttowardl**|\<math.h>|\<math.h> oder \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> oder \<cfloat>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
