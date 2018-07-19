---
title: nextafter, nextafterf, nextafterl, _nextafter, _nextafterf, nexttoward, nexttowardf, nexttowardl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c68d039ff1318ea082d409078a55c8d337a48de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403715"
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

Gibt den nächsten darstellbaren Gleitkomma-Wert des Rückgabetyps nach *x* in Richtung der *y*. Wenn *x* und *y* gleich sind, gibt die Funktion *y*, umgewandelt in den Rückgabetyp mit keine Ausnahme ausgelöst. Wenn *x* stimmt nicht mit *y*, und das Ergebnis ist eine Denormal oder 0 (null), die **FE_UNDERFLOW** und **FE_INEXACT** Gleitkommaausnahme Zustände festgelegt sind, und das richtige Ergebnis zurückgegeben wird. Wenn entweder *x* oder *y* eine NAN ist, dann ist der Rückgabewert eine Eingabe NANs. Wenn *x* ist endlich, und das Ergebnis unendlich oder nicht im Typ darstellbar ist, eine ordnungsgemäß signierten unendlich oder "NaN" zurückgegeben, die **FE_OVERFLOW** und **FE_INEXACT** Gleitkommaausnahmen Status festgelegt sind, und **Errno** festgelegt ist, um **ERANGE**.

## <a name="remarks"></a>Hinweise

Die **Nextafter** und **Nexttoward** Familien Funktion sind gleichwertig, mit Ausnahme der Parametertyp der *y*. Wenn *x* und *y* gleich sind, ist der zurückgegebene Wert *y* zu diesem Rückgabetyp konvertiert.

Da C++ das Überladen zulässt, wenn Sie aufnehmen \<Cmath > können Sie Überladungen von Aufrufen **Nextafter** und **Nexttoward** zurückgegebene **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Nextafter** und **Nexttoward** stets **doppelte**.

Die **_nextafter** und **_nextafterf** Funktionen sind Microsoft-spezifisch. Die **_nextafterf** Funktion ist nur verfügbar, wenn für X64 kompilieren.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|-------------|---------------------------|-------------------------------|
|**Nextafter**, **Nextafterf**, **Nextafterl**, **_nextafterf**, **Nexttoward**, **Nexttowardf** , **Nexttowardl**|\<math.h>|\<math.h> oder \<cmath>|
|**_nextafter**|\<float.h>|\<float.h> oder \<cfloat>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
