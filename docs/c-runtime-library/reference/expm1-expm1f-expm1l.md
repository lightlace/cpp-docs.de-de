---
title: expm1, expm1f, expm1l
ms.date: 04/05/2018
apiname:
- expm1l
- expm1
- expm1f
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
- expm1l
- expm1
- expm1f
helpviewer_keywords:
- expm1f function
- expm1l function
- expm1 function
ms.assetid: 2a4dd2d9-370c-42b0-9067-0625efa272e0
ms.openlocfilehash: 5971f879ecef7d4fa1027849cc44d598e877b5f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441066"
---
# <a name="expm1-expm1f-expm1l"></a>expm1, expm1f, expm1l

Berechnet das base-e-Exponential eines Werts minus eins.

## <a name="syntax"></a>Syntax

```C
double expm1(
   double x
);
float expm1(
   float x
);  // C++ only
long double expm1(
   long double x
);  // C++ only
float expm1f(
   float x
);
long double expm1l(
   long double x
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Das Exponential des Gleitkommawerts.

## <a name="return-value"></a>Rückgabewert

Die **expm1** Funktionen geben einen Gleitkommawert an, die e darstellt zurück<sup>x</sup> - 1, wenn erfolgreich. Bei einem Überlauf **expm1** gibt **HUGE_VAL**, **expm1f** gibt **HUGE_VALF**, **expm1l** zurückgibt **HUGE_VALL**, und **Errno** nastaven NA hodnotu **ERANGE**. Weitere Informationen zu diesen Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **expm1** verwenden und zurückgeben **"float"** und **lange** **doppelte** Werte. In einem C-Programm **expm1** immer Double und gibt eine **doppelte**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**expm1**, **expm1f**, **expm1l**|\<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[pow, powf, powl](pow-powf-powl.md)<br/>
