---
title: sqrt, sqrtf, sqrtl
ms.date: 04/05/2018
api_name:
- sqrtl
- sqrtf
- sqrt
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- sqrt
- sqrtf
- _sqrtl
helpviewer_keywords:
- sqrtf function
- sqrt function
- sqrtl function
- _sqrtl function
- calculating square roots
- square roots, calculating
ms.assetid: 2ba9467b-f172-41dc-8f10-b86f68fa813c
ms.openlocfilehash: 9805141a630afc123c19416595b2a96bc801eee3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958107"
---
# <a name="sqrt-sqrtf-sqrtl"></a>sqrt, sqrtf, sqrtl

Berechnet die Quadratwurzel.

## <a name="syntax"></a>Syntax

```C
double sqrt(
   double x
);
float sqrt(
   float x
);  // C++ only
long double sqrt(
   long double x
);  // C++ only
float sqrtf(
   float x
);
long double sqrtl(
   long double x
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Nicht negativer Gleitkommawert

## <a name="remarks"></a>Hinweise

Da C++ das überladen zulässt, können Sie über Ladungen von **sqrt** aufzurufen, die **float** -oder **Long** **Double** -Typen annehmen. In einem C-Programm nimmt **sqrt** immer einen **Double**-Wert an und gibt ihn zurück.

## <a name="return-value"></a>Rückgabewert

Die **sqrt** -Funktionen geben die Quadratwurzel von *x*zurück. Wenn *x* negativ ist, gibt **sqrt** standardmäßig einen unbestimmten NaN-Wert zurück.

|Eingabe|SEH-Ausnahme|**_matherr** Distanzieren|
|-----------|-------------------|--------------------------|
|± QNAN,IND|none|_DOMAIN|
|- ∞|none|_DOMAIN|
|x<0|none|_DOMAIN|

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**sqrt**, **sqrtf**, **sqrtl**|\<math.h>|\<cmath>|

Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_sqrt.c
// This program calculates a square root.

#include <math.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   double question = 45.35, answer;
   answer = sqrt( question );
   if( question < 0 )
      printf( "Error: sqrt returns %f\n", answer );
   else
      printf( "The square root of %.2f is %.2f\n", question, answer );
}
```

```Output
The square root of 45.35 is 6.73
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[exp, expf, expl](exp-expf.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
[pow, powf, powl](pow-powf-powl.md)<br/>
[_CIsqrt](../../c-runtime-library/cisqrt.md)<br/>
