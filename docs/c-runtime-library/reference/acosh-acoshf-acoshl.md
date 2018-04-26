---
title: acosh, acoshf, acoshl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- acoshf
- acosh
- acoshl
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
- acosh
- acoshf
- acoshl
- math/acosh
- math/acoshf
- math/acoshl
dev_langs:
- C++
helpviewer_keywords:
- acoshf function
- acosh function
- acoshl function
ms.assetid: 6985c4d7-9e2a-44ce-9a9b-5a43015f15f7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cde187ddcb082c468215c00294b08d183b73323a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="acosh-acoshf-acoshl"></a>acosh, acoshf, acoshl

Berechnet den umgekehrten hyperbolischen Cosinus.

## <a name="syntax"></a>Syntax

```C
double acosh( double x );
float acoshf( float x );
long double acoshl( long double x );
```

```cpp
float acosh( float x );  // C++ only
long double acosh( long double x );  // C++ only
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkommawert.

## <a name="return-value"></a>Rückgabewert

Die **Acosh** Funktionen geben den umgekehrten hyperbolischen Cosinus (hyperbolischen arcuscosinus) von *x*. Diese Funktionen sind in der Domäne gültig *x* ≥ 1. Wenn *x* ist kleiner als 1, **Errno** festgelegt ist, um **EDOM** und das Ergebnis ist ein stilles NaN. Wenn *x* ist ein stilles NaN, undefiniert oder unendlich ist, wird der gleiche Wert zurückgegeben.

|Eingabe|SEH-Ausnahme|**_matherr** Ausnahme|
|-----------|-------------------|--------------------------|
|± QNAN, IND, INF|Keine|Keine|
|*X* < 1|Keine|Keine|

## <a name="remarks"></a>Hinweise

Wenn Sie C++ verwenden, können Sie Überladungen von Aufrufen **Acosh** verwenden und zurückgeben **"float"** oder **lange** **doppelte** Werte. In einem C-Programm **Acosh** immer Double und gibt **doppelte**.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**Acosh**, **Acoshf**, **Acoshl**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_acosh.c
// Compile by using: cl /W4 crt_acosh.c
// This program displays the hyperbolic cosine of pi / 4
// and the arc hyperbolic cosine of the result.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double pi = 3.1415926535;
   double x, y;

   x = cosh( pi / 4 );
   y = acosh( x );
   printf( "cosh( %f ) = %f\n", pi/4, x );
   printf( "acosh( %f ) = %f\n", x, y );
}
```

```Output
cosh( 0.785398 ) = 1.324609
acosh( 1.324609 ) = 0.785398
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[asinh, asinhf, asinhl](asinh-asinhf-asinhl.md)<br/>
[atanh, atanhf, atanhl](atanh-atanhf-atanhl.md)<br/>
[cosh, coshf, coshl](cosh-coshf-coshl.md)<br/>
[sinh, sinhf, sinhl](sinh-sinhf-sinhl.md)<br/>
[tanh, tanhf, tanhl](tanh-tanhf-tanhl.md)<br/>
