---
title: remainder, remainderf, remainderl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- remainderl
- remainder
- remainderf
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
- remainderf
- remainder
- remainderl
dev_langs:
- C++
helpviewer_keywords:
- remainderf
- remainderl
- remainder
ms.assetid: 5f721fb3-8b78-4597-9bc0-ca9bcd1f1d0e
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52abbfef2e20bebd531ef2d6c7a414f8345d996b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="remainder-remainderf-remainderl"></a>remainder, remainderf, remainderl

Berechnet den Rest des Quotienten aus zwei Gleitkommawerten, gerundet auf den nächsten ganzzahligen Wert.

## <a name="syntax"></a>Syntax

```C
double remainder( double x, double y );
float remainderf( float x, float y );
long double remainderl( long double x, long double y );
```

```cpp
float remainder( float x, float y ); /* C++ only */
long double remainder( long double x, long double y ); /* C++ only */
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der Zähler.

*y*<br/>
Der Nenner.

## <a name="return-value"></a>Rückgabewert

Den Gleitkommarest von *x* / *y*. Wenn der Wert der *y* ist "0,0", " **Rest** gibt ein stilles NaN zurück. Informationen zu der Darstellung des ein stilles NaN, durch die **Printf** Familie finden Sie unter [Printf, _printf_l, Wprintf _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="remarks"></a>Hinweise

Die **Rest** Funktionen berechnet den Gleitkommarest *r* von *x* / *y* so, dass *x*   =  *n* * *y* + *r*, wobei *n*ist die in den Wert, der nächste Ganzzahl *x* / *y* und *n*ist auch bei jedem &#124; *n*  -  *x* / *y* &#124; = 1/2. Wenn *r* = 0, *r* hat die gleichen Vorzeichen wie *x*.

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Rest** verwenden und zurückgeben **"float"** oder **lange** **doppelte** Werte. In einem C-Programm **Rest** immer zwei **doppelte** Argumente und gibt eine **doppelte**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|--------------|---------------------|-|
|**Rest**, **Remainderf**, **Remainderl**|\<math.h>|\<cmath> oder \<math.h>|

Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_remainder.c
// This program displays a floating-point remainder.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double w = -10.0, x = 3.0, z;

   z = remainder(w, x);
   printf("The remainder of %.2f / %.2f is %f\n", w, x, z);
}
```

```Output
The remainder of -10.00 / 3.00 is -1.000000
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[ldiv, lldiv](ldiv-lldiv.md)<br/>
[imaxdiv](imaxdiv.md)<br/>
[fmod, fmodf](fmod-fmodf.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
