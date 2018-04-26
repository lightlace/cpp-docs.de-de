---
title: scalbn scalbnf, scalbnl, scalbln, scalblnf, scalblnl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- scalblnl
- scalbnl
- scalbnf
- scalblnf
- scalbn
- scalbln
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
- scalblnf
- scalbnl
- scalblnl
- scalbln
- scalbn
- scalbnf
dev_langs:
- C++
helpviewer_keywords:
- scalbn function
- scalbln function
- scalblnl function
- scalbnl function
- scalbnf function
- scalblnf function
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 111978053b35b73a4b5ef9b07e1ecb987d84f6bf
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="scalbn-scalbnf-scalbnl-scalbln-scalblnf-scalblnl"></a>scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl

Multipliziert eine Gleitkommazahl mit einer ganzzahligen Potenz von FLT_RADIX.

## <a name="syntax"></a>Syntax

```C
double scalbn(
   double x,
   int exp
);
float scalbn(
   float x,
   int exp
);  // C++ only
long double scalbn(
   long double x,
   int exp
);  // C++ only
float scalbnf(
   float x,
   int exp
);
long double scalbnl(
   long double x,
   int exp
);
double scalbln(
   double x,
   long exp
);
float scalbln(
   float x,
   long exp
);  // C++ only
long double scalbln(
   long double x,
   long exp
);  // C++ only
float scalblnf(
   float x,
   long exp
);
long double scalblnl(
   long double x,
   long exp
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkommawert.

*exp*<br/>
Ganzzahlexponent.

## <a name="return-value"></a>Rückgabewert

Die **Scalbn** Funktionen Rückgabe des Werts der *x* * **FLT_RADIX**<sup>exp</sup> bei erfolgreicher Ausführung. Bei einem Überlauf (abhängig vom Vorzeichen des *x*), **Scalbn** gibt **HUGE_VAL**; das **Errno** Wert wird festgelegt, um **ERANGE** .

Weitere Informationen zu **Errno** und potenzieller Fehler Werte zurückgeben, finden Sie unter [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

**FLT_RADIX** ist definiert \<float.h > als native gleitkommabasis; in binären Systemen hat es den Wert 2, und **Scalbn** entspricht [Ldexp](ldexp.md).

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Scalbn** und **Scalbln** verwenden und zurückgeben **"float"** oder **lange** **doppelte** Typen. In einem C-Programm **Scalbn** immer ein **doppelte** und ein **Int** und gibt eine **doppelte**, und **Scalbln**immer ein **doppelte** und ein **lange** und gibt eine **doppelte**.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**Scalbn**, **Scalbnf**, **Scalbnl**, **Scalbln**, **Scalblnf**, **Scalblnl**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_scalbn.c
// Compile using: cl /W4 crt_scalbn.c
#include <math.h>
#include <stdio.h>

int main( void )
{
   double x = 6.4, y;
   int p = 3;

   y = scalbn( x, p );
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );
}
```

### <a name="output"></a>Ausgabe

```Output
6.4 times FLT_RADIX to the power of 3 is 51.2
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
[ldexp](ldexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
