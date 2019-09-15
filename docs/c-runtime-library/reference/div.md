---
title: div, ldiv, lldiv
ms.date: 04/05/2018
api_name:
- div
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
- api-ms-win-crt-utility-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- div
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
ms.openlocfilehash: 5b40fa0c4cc9cdf0c0de0f6af21da04b0c70369f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70937694"
---
# <a name="div-ldiv-lldiv"></a>div, ldiv, lldiv

Berechnet den Quotienten und den Rest von zwei ganzzahligen Werten.

## <a name="syntax"></a>Syntax

```C
div_t div(
   int numer,
   int denom
);
ldiv_t ldiv(
   long numer,
   long denom
);
lldiv_t lldiv(
   long long numer,
   long long denom
);
```

```cpp
ldiv_t div(
   long numer,
   long denom
); /* C++ only */
lldiv_t div(
   long long numer,
   long long denom
); /* C++ only */
```

### <a name="parameters"></a>Parameter

*Zahl*<br/>
Der Zähler.

*Denom*<br/>
Der Nenner.

## <a name="return-value"></a>Rückgabewert

mithilfe von Argumenten des Typs **int** aufgerufene **div** gibt eine Struktur vom Typ **div_t**zurück, die den Quotienten und den Rest enthält. Der Rückgabewert mit Argumenten vom Typ **Long** ist **ldiv_t**, und der Rückgabewert mit Argumenten vom Typ **Long** **Long** ist **lldiv_t**. **div_t**, **ldiv_t**und **lldiv_t** sind in \<STDLIB. h > definiert.

## <a name="remarks"></a>Hinweise

Die **div** -Funktion dividiert den *Zahl* durch *denom* und berechnet dadurch den Quotienten und den Rest. Die [div_t](../../c-runtime-library/standard-types.md) -Struktur enthält den Quotienten, **quot**und den Rest, **REM**. Das Zeichen des Quotienten entspricht dem Zeichen des mathematischen Quotienten. Der absolute Wert ist die größte ganze Zahl, die kleiner ist als der absolute Wert des mathematischen Quotienten. Wenn der Nenner 0 ist, wird das Programm mit einer Fehlermeldung beendet.

Die über Ladungen von **div** , die Argumente vom Typ " **Long** " oder " **Long** **Long** " C++ akzeptieren, sind nur für Code verfügbar. Die Rückgabe Typen [ldiv_t](../../c-runtime-library/standard-types.md) und [lldiv_t](../../c-runtime-library/standard-types.md) enthalten die Member **quot** und **REM**, die die gleiche Bedeutung wie die Member von **div_t**haben.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**div**, **ldiv**, **lldiv**|\<stdlib.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_div.c
// arguments: 876 13

// This example takes two integers as command-line
// arguments and displays the results of the integer
// division. This program accepts two arguments on the
// command line following the program name, then calls
// div to divide the first argument by the second.
// Finally, it prints the structure members quot and rem.
//

#include <stdlib.h>
#include <stdio.h>
#include <math.h>

int main( int argc, char *argv[] )
{
   int x,y;
   div_t div_result;

   x = atoi( argv[1] );
   y = atoi( argv[2] );

   printf( "x is %d, y is %d\n", x, y );
   div_result = div( x, y );
   printf( "The quotient is %d, and the remainder is %d\n",
           div_result.quot, div_result.rem );
}
```

```Output
x is 876, y is 13
The quotient is 67, and the remainder is 5
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
