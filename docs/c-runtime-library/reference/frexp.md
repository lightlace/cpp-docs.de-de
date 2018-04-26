---
title: Frexp, Frexpf, Frexpl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- frexp
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
- frexp
- _frexpl
dev_langs:
- C++
helpviewer_keywords:
- _frexpl function
- mantissas, floating-point variables
- frexpl function
- exponent, floating-point numbers
- frexp function
- floating-point functions, mantissa and exponent
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed4f3096b52834b59250226d7857ed0069982749
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="frexp-frexpf-frexpl"></a>Frexp, Frexpf, frexpl

Ruft die Mantisse und den Exponenten einer Gleitkommazahl ab

## <a name="syntax"></a>Syntax

```C
double frexp(
   double x,
   int *expptr
);
float frexpf(
   float x,
   int * expptr
);
long double frexpl(
   long double x,
   int * expptr
);
float frexp(
   float x,
   int * expptr
);  // C++ only
long double frexp(
   long double x,
   int * expptr
);  // C++ only
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkommawert.

*expptr*<br/>
Zeiger auf gespeicherten Integer-Exponenten

## <a name="return-value"></a>Rückgabewert

**Frexp** gibt die Mantisse. Wenn *x* gleich 0 ist, die Funktion gibt 0 für die Mantisse und dem Exponenten zurück. Wenn *Expptr* ist **NULL**, den Handler für ungültige Parameter aufgerufen wird, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt diese Funktion **Errno** auf **EINVAL** und gibt 0 zurück.

## <a name="remarks"></a>Hinweise

Die **Frexp** -Funktion gliedert den Gleitkommawert (*x*) in einer Mantisse (*m*) und einen Exponenten (*n*), sodass der Absolute Wert des *m* ist größer als oder gleich 0,5 und kleiner als 1,0 und *x* = *m* * 2<sup>*n*</sup>. Die ganzzahlexponent *n* an der Speicherstelle gespeichert *Expptr*.

C++ das Überladen zulässt, sodass Sie Überladungen von aufrufen können **Frexp**. In einem C-Programm **Frexp** immer ein **doppelte** und ein **Int** Zeiger und gibt eine **doppelte**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**Frexp**, **Frexpf**, **Frexpl**|\<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_frexp.c
// This program calculates frexp( 16.4, &n )
// then displays y and n.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double x, y;
   int n;

   x = 16.4;
   y = frexp( x, &n );
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );
}
```

```Output
frexp( 16.400000, &n ) = 0.512500, n = 5
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
[modf, modff, modfl](modf-modff-modfl.md)<br/>
