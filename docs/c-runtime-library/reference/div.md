---
title: Div, Ldiv, Lldiv | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- div
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- div
dev_langs:
- C++
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ba1625105adf6edbc6419bd4fdabc8bda5d0e98
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396591"
---
# <a name="div-ldiv-lldiv"></a>Div, Ldiv, lldiv

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

*Anzahl*<br/>
Der Zähler.

*Denom*<br/>
Der Nenner.

## <a name="return-value"></a>Rückgabewert

**Div** mithilfe von Argumenten des Typs aufgerufen **Int** gibt eine Struktur des Typs **Div_t**, die besteht aus den Quotienten und den Rest enthält. Der Rückgabewert mit Argumenten vom Typ **lange** ist **Ldiv_t**, und der Rückgabewert mit Argumenten vom Typ **lange** **lange** ist**Lldiv_t**. **Div_t**, **Ldiv_t**, und **Lldiv_t** im definiert \<stdlib.h >.

## <a name="remarks"></a>Hinweise

Die **Div** -Funktion teilt *Anzahl* von *Denom* und berechnet dadurch den Quotienten und den Rest enthält. Die [Div_t](../../c-runtime-library/standard-types.md) Struktur enthält den Quotienten **Quot**, und der Rest **Rem**. Das Zeichen des Quotienten entspricht dem Zeichen des mathematischen Quotienten. Der absolute Wert ist die größte ganze Zahl, die kleiner ist als der absolute Wert des mathematischen Quotienten. Wenn der Nenner 0 ist, wird das Programm mit einer Fehlermeldung beendet.

Überladungen der **Div** , die Argumente des Typs **lange** oder **lange** **lange** sind nur für C++-Code verfügbar. Die Rückgabetypen [Ldiv_t](../../c-runtime-library/standard-types.md) und [Lldiv_t](../../c-runtime-library/standard-types.md) enthält Elemente **Quot** und **Rem**, wofür dieselbe Bedeutung wie die Member des **Div_t**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**Div**, **Ldiv**, **Lldiv**|\<stdlib.h>|

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
