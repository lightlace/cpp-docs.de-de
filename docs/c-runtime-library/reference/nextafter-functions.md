---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl
ms.date: 04/05/2018
apiname:
- nextafterf
- _nextafterf
- nextafter
- nextafterl
- _nextafter
- nexttoward
- nexttowardf
- nexttowardl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 0e0a60dc9f7c068d8c18c10f3c6b819b9e06d3b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156186"
---
# <a name="nextafter-nextafterf-nextafterl-nextafter-nextafterf-nexttoward-nexttowardf-nexttowardl"></a>nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl

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

Gibt den nächsten darstellbaren Gleitkommawert des Rückgabetyps nach *x* in Richtung der *y*. Wenn *x* und *y* gleich sind, die Funktion gibt *y*, konvertiert in den Rückgabetyp, ohne eine Ausnahme ausgelöst. Wenn *x* ist nicht gleich *y*, und das Ergebnis eine subnormale oder 0 (null), die **FE_UNDERFLOW** und **FE_INEXACT** Gleitkomma-Ausnahmezustände festgelegt sind, und das richtige Ergebnis zurückgegeben wird. Wenn entweder *x* oder *y* ist ein NaN-Wert, dann ist der Rückgabewert eines Eingabe-NaN. Wenn *x* ist begrenzt und das Ergebnis unendlich oder nicht im Typ darstellbar ist, eine ordnungsgemäß signierten Unendlichkeit oder NAN zurückgegeben, die **FE_OVERFLOW** und **FE_INEXACT** Gleitkomma-Ausnahmezustände festgelegt sind, und **Errno** nastaven NA hodnotu **ERANGE**.

## <a name="remarks"></a>Hinweise

Die **Nextafter** und **Nexttoward** -funktionsfamilien sind mit Ausnahme der Parametertyp des entsprechenden *y*. Wenn *x* und *y* gleich sind, ist der zurückgegebene Wert *y* in den Rückgabetyp konvertiert.

Da C++ das Überladen zulässt, wenn Sie einschließen \<Cmath > können Sie Überladungen von Aufrufen **Nextafter** und **Nexttoward** zurückgegebene **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Nextafter** und **Nexttoward** jederzeit **doppelte**.

Die **_nextafter** und **_nextafterf** Funktionen sind Microsoft-spezifisch. Die **_nextafterf** Funktion ist nur verfügbar, beim Kompilieren für X64.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|-------------|---------------------------|-------------------------------|
|**nextafter**, **nextafterf**, **nextafterl**, **_nextafterf**, **nexttoward**, **nexttowardf**, **nexttowardl**|\<math.h>|\<math.h> oder \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> oder \<cfloat>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
