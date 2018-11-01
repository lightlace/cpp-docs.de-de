---
title: asinh, asinhf, asinhl
ms.date: 04/05/2018
apiname:
- asinh
- asinhf
- asinhl
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
- asinhf
- asinhl
- asinh
helpviewer_keywords:
- asinh function
- asinhl function
- asinhf function
ms.assetid: 4488babe-1a7e-44ca-8b7b-c2db0a70084f
ms.openlocfilehash: f6100268b77178487b7a7aa1cc3f10ac3ea7e9dc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662955"
---
# <a name="asinh-asinhf-asinhl"></a>asinh, asinhf, asinhl

Berechnet den umgekehrten hyperbolischen Sinus.

## <a name="syntax"></a>Syntax

```C
double asinh( double x );
float asinhf( float x );
long double asinhl( long double x );
```

```cpp
float asinh( float x );  // C++ only
long double asinh( long double x );  // C++ only
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkommawert.

## <a name="return-value"></a>Rückgabewert

Die **Asinh** Funktionen geben den umgekehrten hyperbolischen Sinus (hyperbolischen Arkussinus) *x*. Diese Funktion ist über der Gleitkommadomäne gültig. Wenn *x* wird eine stille NaN, undefiniert oder unendlich ist, wird der gleiche Wert zurückgegeben.

|Eingabe|SEH-Ausnahme|**_matherr** Ausnahme|
|-----------|-------------------|--------------------------|
|± QNAN, IND, INF|Keine|Keine|

## <a name="remarks"></a>Hinweise

Wenn Sie C++ verwenden, können Sie Überladungen von Aufrufen **Asinh** verwenden und zurückgeben **"float"** oder **lange** **doppelte** Werte. In einem C-Programm **Asinh** immer Double und gibt **doppelte**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher C-Header|Erforderlicher C++-Header|
|--------------|--------------|------------------|
|**Asinh**, **Asinhf**, **Asinhl**|\<math.h>|\<Cmath > oder \<math.h <|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_asinh.c
// Compile by using: cl /W4 crt_asinh.c
// This program displays the hyperbolic sine of pi / 4
// and the arc hyperbolic sine of the result.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = sinh( pi / 4 );
   y = asinh( x );
   printf( "sinh( %f ) = %f\n", pi/4, x );
   printf( "asinh( %f ) = %f\n", x, y );
}
```

```Output
sinh( 0.785398 ) = 0.868671
asinh( 0.868671 ) = 0.785398
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[acosh, acoshf, acoshl](acosh-acoshf-acoshl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[cosh, coshf, coshl](cosh-coshf-coshl.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
