---
title: modf, modff, modfl
ms.date: 04/05/2018
apiname:
- modff
- modf
- modfl
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
ms.openlocfilehash: 59d6e2b9b02ad182c5630d6dc9a989c035e8fa92
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478064"
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

*IntPtr*<br/>
Zeiger auf gespeicherten Ganzzahlbereich.

## <a name="return-value"></a>Rückgabewert

Diese Funktion gibt den Bruchteil von *x* mit Vorzeichen zurück. Es gibt keine Fehlerrückgabe.

## <a name="remarks"></a>Hinweise

Die **Modf** Funktionen beeinträchtigen den Gleitkommawert *x* in Nachkommastellen und ganze Zahlen, von denen jedes die gleichen Vorzeichen wie hat *x*. Der signierte Bruchteil von *x* zurückgegeben wird. Der ganzzahlige Teil wird als Gleitkommawert unter gespeichert *Intptr*.

**Modf** verfügt über eine Implementierung, Streaming SIMD Extensions 2 (SSE2) verwendet. Informationen und Einschränkungen zur Verwendung der SSE2-Implementierung finden Sie unter [_set_SSE2_enable](set-sse2-enable.md).

Da C++ das Überladen zulässt, können Sie Überladungen von aufrufen können **Modf** verwenden und zurückgeben **"float"** oder **lange** **doppelte** Parameter. In einem C-Programm **Modf** immer zwei double-Werten und gibt einen doppelten Wert zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**Modf**, **Modff**, **Modfl**|C: \<math.h><br /><br /> C++: , \<cmath> oder \<math.h>|

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
