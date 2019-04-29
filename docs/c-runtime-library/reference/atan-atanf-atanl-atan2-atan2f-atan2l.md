---
title: atan, atanf, atanl, atan2, atan2f, atan2l
ms.date: 04/05/2018
apiname:
- atan2f
- atan2l
- atan2
- atanf
- atan
- atanl
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
- atan
- atan2l
- atan2
- atanl
- atanf
- atan2f
helpviewer_keywords:
- atan function
- atanf function
- atanl function
- atan2 function
- atan2l function
- arctangent function
- trigonometric functions
- atan2f function
ms.assetid: 7a87a18e-c94d-4727-9cb1-1bb5c2725ae4
ms.openlocfilehash: 59a67b0d213a11630f551fd7582b44aab60e314f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341716"
---
# <a name="atan-atanf-atanl-atan2-atan2f-atan2l"></a>atan, atanf, atanl, atan2, atan2f, atan2l

Berechnet den Arkustangens des **x** (**Atan**, **Atanf**, und **Atanl**) oder den Arkustangens von **y** / **x** (**atan2**, **atan2f**, und **atan2l**).

## <a name="syntax"></a>Syntax

```C
double atan( double x );
float atanf( float x );
long double atanl( long double x );

double atan2( double y, double x );
float atan2f( float y, float x );
long double atan2l( long double y, long double x );
```

```cpp
float atan( float x );  // C++ only
long double atan( long double x );  // C++ only

float atan2( float y, float x );  // C++ only
long double atan2( long double y, long double x );  // C++ only
```

### <a name="parameters"></a>Parameter

*x*, *y*<br/>
Alle Zahlen.

## <a name="return-value"></a>Rückgabewert

**ATAN** gibt den Arkustangens der *x* im Bereich - π/2 auf π/2-Bogenmaßes zurück. **atan2** gibt den Arkustangens der *y*/*x* in den Bereich - π π Bogenmaß. Wenn *x* ist 0 (null) **Atan** gibt 0 zurück. Wenn beide Parameter von **atan2** 0 sind, gibt die Funktion 0 zurück. Alle Ergebnisse sind in Bogenmaß.

**atan2** verwendet Sie die Zeichen beider Parameter, um den Quadranten des Rückgabewerts zu bestimmen.

|Eingabe|SEH-Ausnahme|Matherr-Ausnahme|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|none|**_DOMAIN**|

## <a name="remarks"></a>Hinweise

Die **Atan** -Funktion berechnet den Arkustangens (die umgekehrte Tangensfunktion) von *x*. **atan2** berechnet den Arkustangens des *y*/*x* (Wenn *x* gleich 0 ist, **atan2** π/2 zurück, wenn *y* positiv ist, - π/2-If *y* ist negativ oder 0, wenn *y* ist 0.)

**ATAN** verfügt über eine Implementierung, Streaming SIMD Extensions 2 (SSE2) verwendet. Informationen und Einschränkungen zur Verwendung der SSE2-Implementierung finden Sie unter [_set_SSE2_enable](set-sse2-enable.md).

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Atan** und **atan2** , Take **"float"** oder **lange** **double**  Argumente. In einem C-Programm **Atan** und **atan2** immer **doppelte** Argumenten und Rückgabetypen einer **doppelte**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|-------------|---------------------|-|
|**atan**, **atan2**, **atanf**, **atan2f**, **atanl**, **atan2l**|\<math.h>|\<cmath> oder \<math.h>|

## <a name="example"></a>Beispiel

```C
// crt_atan.c
// arguments: 5 0.5
#include <math.h>
#include <stdio.h>
#include <errno.h>

int main( int ac, char* av[] )
{
   double x, y, theta;
   if( ac != 3 ){
      fprintf( stderr, "Usage: %s <x> <y>\n", av[0] );
      return 1;
   }
   x = atof( av[1] );
   theta = atan( x );
   printf( "Arctangent of %f: %f\n", x, theta );
   y = atof( av[2] );
   theta = atan2( y, x );
   printf( "Arctangent of %f / %f: %f\n", y, x, theta );
   return 0;
}
```

```Output
Arctangent of 5.000000: 1.373401
Arctangent of 0.500000 / 5.000000: 0.099669
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[asin, asinf, asinl](asin-asinf-asinl.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
[_CIatan](../../c-runtime-library/ciatan.md)<br/>
[_CIatan2](../../c-runtime-library/ciatan2.md)<br/>
