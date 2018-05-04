---
title: Pow, Powf, Powl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- powl
- pow
- powf
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
- powl
- pow
- _powl
- powf
dev_langs:
- C++
helpviewer_keywords:
- exponential calculations
- powl function
- _powl function
- exponentiation
- powers, calculating
- calculating exponentials
- powf function
- pow function
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5daf7348198cb6f3ba0186eb4586b2486548f6f5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="pow-powf-powl"></a>pow, powf, powl

Berechnet *x* potenziert mit der *y*.

## <a name="syntax"></a>Syntax

```C
double pow( double x, double y );
float powf( float x, float y );
long double powl( long double x, long double y );
```

```cpp
double pow( double x, int y );  // C++ only
float pow( float x, float y );  // C++ only
float pow( float x, int y );  // C++ only
long double pow( long double x, long double y );  // C++ only
long double pow( long double x, int y );  // C++ only
```

### <a name="parameters"></a>Parameter

*w*<br/>
Basis.

*y*<br/>
Exponent.

## <a name="return-value"></a>Rückgabewert

Gibt den Wert der *x*<sup>*y*</sup>. Zu Überlauf oder Unterlauf wird keine Fehlermeldung ausgegeben.

|Werte von x und y|Rückgabewert von "pow"|
|-----------------------|-------------------------|
|*X* ! = 0,0 und *y* == 0,0|1|
|*X* == 0,0 und *y* == 0,0|1|
|*X* == 0,0 und *y* < 0|INF|

## <a name="remarks"></a>Hinweise

**Pow** erkennt keine ganzzahligen Gleitkommawerte größer als 2<sup>64</sup> (z. B. 1.0E100).

**Pow** ist eine Implementierung, die Streaming SIMD Extensions 2 (SSE2) verwendet. Informationen und Einschränkungen zur Verwendung der SSE2-Implementierung finden Sie unter [_set_SSE2_enable](set-sse2-enable.md).

Da C++ das Überladen zulässt, können Sie eine der verschiedenen Überladungen von Aufrufen **pow**. In einem C-Programm **pow** immer zwei **doppelte** Werte und gibt eine **doppelte** Wert.

Die `pow(int, int)`-Überladung ist nicht mehr verfügbar. Wenn Sie diese Überladung verwenden, kann der Compiler nicht aus [C2668](../../error-messages/compiler-errors-2/compiler-error-c2668.md). Um dieses Problem zu vermeiden, wandeln Sie den ersten Parameter an **doppelte**, **"float"**, oder **lange** **doppelte**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|-|-|-|
|**Pow**, **Powf**, **Powl**|\<math.h>|\<math.h> oder \<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_pow.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.0, y = 3.0, z;

   z = pow( x, y );
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );
}
```

```Output
2.0 to the power of 3.0 is 8.0
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md) <br/>
[exp, expf, expl](exp-expf.md) <br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md) <br/>
[sqrt, sqrtf, sqrtl](sqrt-sqrtf-sqrtl.md) <br/>
[_CIpow](../../c-runtime-library/cipow.md)<br/>
