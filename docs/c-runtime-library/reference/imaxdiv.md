---
title: imaxdiv
ms.date: 04/05/2018
apiname:
- imaxdiv
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
- imaxdiv
helpviewer_keywords:
- imaxdiv function
ms.assetid: 7d90126f-fdc2-4986-9cdf-94e4c9123d26
ms.openlocfilehash: 23067b2028fc11193fae707e25165fb0ce754515
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157330"
---
# <a name="imaxdiv"></a>imaxdiv

Berechnet den Quotienten und den Rest von zwei ganzzahligen Werten beliebiger Größe als einzelnen Vorgang.

## <a name="syntax"></a>Syntax

```C
imaxdiv_t imaxdiv(
   intmax_t numer,
   intmax_t denom
);
```

### <a name="parameters"></a>Parameter

*numer*<br/>
Der Zähler.

*denom*<br/>
Der Nenner.

## <a name="return-value"></a>Rückgabewert

**Imaxdiv** mit Argumenten des Typs aufgerufen [Intmax_t](../../c-runtime-library/standard-types.md) gibt eine Struktur des Typs [Imaxdiv_t](../../c-runtime-library/standard-types.md) , die besteht aus den Quotienten und den Rest.

## <a name="remarks"></a>Hinweise

Die **Imaxdiv** -Funktion teilt *Anzahl* von *Denom* und berechnet dadurch den Quotienten und den Rest. Die **Imaxdiv_t** Struktur enthält den Quotienten **Intmax_t** **Quot**, und den Rest **Intmax_t** **Rem**. Das Zeichen des Quotienten entspricht dem Zeichen des mathematischen Quotienten. Der absolute Wert ist die größte ganze Zahl, die kleiner ist als der absolute Wert des mathematischen Quotienten. Wenn der Nenner 0 ist, wird das Programm mit einer Fehlermeldung beendet.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**imaxdiv**|\<inttypes.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_imaxdiv.c
// Build using: cl /W3 /Tc crt_imaxdiv.c
// This example takes two integers as command-line
// arguments and calls imaxdiv to divide the first
// argument by the second, then displays the results.

#include <stdio.h>
#include <stdlib.h>
#include <inttypes.h>

int main(int argc, char *argv[])
{
   intmax_t x,y;
   imaxdiv_t div_result;

   x = atoll(argv[1]);
   y = atoll(argv[2]);

   printf("The call to imaxdiv(%lld, %lld)\n", x, y);
   div_result = imaxdiv(x, y);
   printf("results in a quotient of %lld, and a remainder of %lld\n\n",
          div_result.quot, div_result.rem);
}
```

Wenn der Code mit den Befehlszeilenparametern von `9460730470000000 8766` erstellt und anschließend aufgerufen wird, wird diese Ausgabe generiert:

```Output
The call to imaxdiv(9460730470000000, 8766)
results in a quotient of 1079252848505, and a remainder of 5170
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[div](div.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
