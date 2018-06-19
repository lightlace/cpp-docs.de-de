---
title: 'Bessel-Funktionen: _j0, _j1, _jn, _y0, _y1, _yn | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _j0
- _j1
- _jn
- _y0
- _y1
- _yn
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
- c.bessel
- _j0
- _j1
- _jn
- _y0
- _y1
- _yn
dev_langs:
- C++
helpviewer_keywords:
- Bessel functions
- _j0 function
- _j1 function
- _jn function
- _y0 function
- _y1 function
- _yn function
ms.assetid: a21a8bf1-df9d-4ba0-a8c2-e7ef71921d96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf461a7737ee1f23650ff80f203524c427fb644d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393601"
---
# <a name="bessel-functions-j0-j1-jn-y0-y1-yn"></a>Bessel-Funktionen: _j0, _j1, _jn, _y0, _y1, _yn

Berechnet die Bessel-Funktion der ersten oder zweiten Art und der 0-ten, 1-ten oder n-ten Ordnung. Die Bessel-Funktionen werden in der mathematischen Behandlung von elektromagnetischen Wellen in breitem Umfang eingesetzt.

## <a name="syntax"></a>Syntax

```C
double _j0(
   double x
);
double _j1(
   double x
);
double _jn(
   int n,
   double x
);
double _y0(
   double x
);
double _y1(
   double x
);
double _yn(
   int n,
   double x
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkommawert.

*n*<br/>
Ganzzahlige Ordnung der Bessel-Funktion.

## <a name="return-value"></a>Rückgabewert

Jede dieser Routinen gibt eine Besselfunktion der *x*. Wenn *x* ist ein negativer Wert in der **_y0**, **_y1**, oder **_yn** Funktionen, legt die Routine **Errno** zu  **EDOM**, druckt eine **_DOMAIN** Fehlermeldung **"stderr"**, und gibt **_HUGE_VAL**. Sie können die Fehlerbehandlung mithilfe **_matherr**.

## <a name="remarks"></a>Hinweise

Die **_j0**, **_j1**, und **_jn** Routinen Rückgabe Bessel-Funktionen der ersten Art: Ordnung 0, 1, n, bzw.

|Eingabe|SEH-Ausnahme|Matherr-Ausnahme|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|**UNGÜLTIG**|**_DOMAIN**|

Die **_y0**, **_y1**, und **_yn** Routinen Rückgabe Bessel-Funktionen der zweiten Art: Ordnung 0, 1, n, bzw.

|Eingabe|SEH-Ausnahme|Matherr-Ausnahme|
|-----------|-------------------|-----------------------|
|± **QNAN**, **IND**|**UNGÜLTIG**|**_DOMAIN**|
|± 0|**ZERODIVIDE**|**_SING**|
|&#124;X&#124; < 0,0|**UNGÜLTIG**|**_DOMAIN**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_j0**, **_j1**, **_jn**, **_y0**, **_y1**, **_yn**|\<cmath> (C++), \<math.h> (C, C++)|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_bessel1.c
#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 2.387;
   int n = 3, c;

   printf( "Bessel functions for x = %f:\n", x );
   printf( "   Kind   Order  Function     Result\n\n" );
   printf( "   First  0      _j0( x )     %f\n", _j0( x ) );
   printf( "   First  1      _j1( x )     %f\n", _j1( x ) );
   for( c = 2; c < 5; c++ )
      printf( "   First  %d      _jn( %d, x )  %f\n", c, c, _jn( c, x ) );
   printf( "   Second 0      _y0( x )     %f\n", _y0( x ) );
   printf( "   Second 1      _y1( x )     %f\n", _y1( x ) );
   for( c = 2; c < 5; c++ )
      printf( "   Second %d      _yn( %d, x )  %f\n", c, c, _yn( c, x ) );
}
```

```Output
Bessel functions for x = 2.387000:
   Kind   Order  Function     Result

   First  0      _j0( x )     0.009288
   First  1      _j1( x )     0.522941
   First  2      _jn( 2, x )  0.428870
   First  3      _jn( 3, x )  0.195734
   First  4      _jn( 4, x )  0.063131
   Second 0      _y0( x )     0.511681
   Second 1      _y1( x )     0.094374
   Second 2      _yn( 2, x )  -0.432608
   Second 3      _yn( 3, x )  -0.819314
   Second 4      _yn( 4, x )  -1.626833
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[_matherr](matherr.md)<br/>
