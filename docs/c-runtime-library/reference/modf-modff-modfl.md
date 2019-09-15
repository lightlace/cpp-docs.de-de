---
title: modf, modff, modfl
ms.date: 04/05/2018
api_name:
- modff
- modf
- modfl
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
- modff
- _modfl
- modf
- modfl
- math/modf
- math/modff
- math/modfl
helpviewer_keywords:
- modf function
- modff function
- modfl function
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
ms.openlocfilehash: 32caadb787031dca0b0726c546a11c5cd6722b82
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951539"
---
# <a name="modf-modff-modfl"></a>modf, modff, modfl

Teilt einen Gleitkommawert in Nachkommastellen und ganze Zahlen.

## <a name="syntax"></a>Syntax

```C
double modf( double x, double * intptr );
float modff( float x, float * intptr );
long double modfl( long double x, long double * intptr );
```

```cpp
float modf( float x, float * intptr );  // C++ only
long double modf( long double x, long double * intptr );  // C++ only
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkommawert.

*intptr*<br/>
Zeiger auf gespeicherten Ganzzahlbereich.

## <a name="return-value"></a>Rückgabewert

Diese Funktion gibt den Bruchteil von *x* mit Vorzeichen zurück. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Die **modf** -Funktionen unterbrechen den Gleit Komma Wert *x* in Bruchteile und ganzzahlige Teile, von denen jedes dasselbe Vorzeichen wie *x*aufweist. Der Wert von *x* mit Vorzeichen wird zurückgegeben. Der ganzzahlige Teil wird als Gleit Komma Wert bei *IntPtr*gespeichert.

**modf** verfügt über eine Implementierung, die Streaming SIMD Extensions 2 (SSE2) verwendet. Informationen und Einschränkungen zur Verwendung der SSE2-Implementierung finden Sie unter [_set_SSE2_enable](set-sse2-enable.md).

C++ermöglicht überladen, sodass Sie über Ladungen von **modf** abrufen können, die **float** -oder **Long** **Double** -Parameter verwenden und zurückgeben. In einem C-Programm übernimmt **modf** immer zwei Double-Werte und gibt einen Double-Wert zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**modf**, **modff**, **modfl**|C: \<math.h><br /><br /> C++: , \<cmath> oder \<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_modf.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y, n;

   x = -14.87654321;      /* Divide x into its fractional */
   y = modf( x, &n );     /* and integer parts            */

   printf( "For %f, the fraction is %f and the integer is %.f\n",
           x, y, n );
}
```

```Output
For -14.876543, the fraction is -0.876543 and the integer is -14
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
