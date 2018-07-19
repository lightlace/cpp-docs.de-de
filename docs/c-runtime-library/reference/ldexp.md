---
title: Ldexp, Ldexpf, Ldexpl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 012315e11ccf2dbe63e32c6208487f324ef29289
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401417"
---
# <a name="ldexp-ldexpf-ldexpl"></a>Ldexp, Ldexpf, ldexpl

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

Die **Ldexp** Funktionen Rückgabe des Werts der *x* * 2<sup>*exp* </sup> bei Erfolg. Bei einem Überlauf und abhängig vom Vorzeichen des *x*, **Ldexp** gibt **HUGE_VAL**; das **Errno** Wert wird festgelegt, um **ERANGE** .

Weitere Informationen zu **Errno** und potenzieller Fehler Werte zurückgeben, finden Sie unter [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Ldexp** nehmen **"float"** oder **lange** **doppelte** Typen. In einem C-Programm **Ldexp** immer ein **doppelte** und ein **Int** und gibt eine **doppelte**.

## <a name="requirements"></a>Anforderungen

|Routine|C-Header|C++-Header|
|-------------|--------------|------------------|
|**Ldexp**, **Ldexpf**, **Ldexpl**|\<math.h>|\<cmath>|

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

## <a name="output"></a>Ausgabe

```Output
4.0 times two to the power of 3 is 32.0
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
