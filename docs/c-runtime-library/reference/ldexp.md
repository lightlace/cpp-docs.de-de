---
title: ldexp, ldexpf, ldexpl
ms.date: 04/05/2018
apiname:
- ldexp
- ldexpf
- ldexpl
- _ldexpl
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
- ldexp
- ldexpf
- ldexpl
- _ldexpl
helpviewer_keywords:
- calculating real numbers
- computing real numbers
- mantissas, floating-point variables
- ldexp function
- ldexpf function
- ldexpl function
- exponent, floating-point numbers
- floating-point functions, mantissa and exponent
ms.assetid: aa7f5310-3879-4f63-ae74-86a39fbdedfa
ms.openlocfilehash: 7fbf89f8d78e8a2ce1018a790350ec986dcab87e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286292"
---
# <a name="ldexp-ldexpf-ldexpl"></a>ldexp, ldexpf, ldexpl

Multipliziert eine Gleitkommazahl mit einer ganzzahligen Potenz von zwei.

## <a name="syntax"></a>Syntax

```C
double ldexp(
   double x,
   int exp
);
float ldexp(
   float x,
   int exp
);  // C++ only
long double ldexp(
   long double x,
   int exp
);  // C++ only
float ldexpf(
   float x,
   int exp
);
long double ldexpl(
   long double x,
   int exp
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkommawert.

*exp*<br/>
Ganzzahlexponent.

## <a name="return-value"></a>Rückgabewert

Die **Ldexp** Funktionen geben den Wert der *x* \* 2<sup>*"exp"* </sup> bei erfolgreicher Ausführung. Bei einem Überlauf und abhängig vom Vorzeichen *x*, **Ldexp** gibt **HUGE_VAL**; die **Errno** Wert wird festgelegt, um **ERANGE** .

Weitere Informationen zu **Errno** und mögliche Rückgabewerte finden Sie unter [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Ldexp** , Take **"float"** oder **lange** **doppelte** Typen. In einem C-Programm **Ldexp** immer eine **doppelte** und **Int** und gibt eine **doppelte**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|C-Header|C++-Header|
|-------------|--------------|------------------|
|**ldexp**, **ldexpf**, **ldexpl**|\<math.h>|\<cmath>|

Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_ldexp.c

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 4.0, y;
   int p = 3;

   y = ldexp( x, p );
   printf( "%2.1f times two to the power of %d is %2.1f\n", x, p, y );
}
```

## <a name="output"></a>Output

```Output
4.0 times two to the power of 3 is 32.0
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
