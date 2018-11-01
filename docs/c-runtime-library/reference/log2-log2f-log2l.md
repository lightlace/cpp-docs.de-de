---
title: log2, log2f, log2l
ms.date: 04/05/2018
apiname:
- log2
- log2l
- log2f
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
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
ms.openlocfilehash: 5f1db48abdc7237dc46a0ea8a3ea5647a0fce62f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579308"
---
# <a name="log2-log2f-log2l"></a>log2, log2f, log2l

Bestimmt den binären Logarithmus (Basis 2) des angegebenen Werts.

## <a name="syntax"></a>Syntax

```C
double log2(
   double x
);

float log2(
   float x
); //C++ only

long double log2(
   long double x
); //C++ only

float log2f(
   float x
);

long double log2l(
   long double x
);

```

### <a name="parameters"></a>Parameter

*w*<br/>
Der Wert, um den Basis 2-Logarithmus zu bestimmen.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg wird log2 gibt *x*.

Andernfalls wird möglicherweise einer der folgenden Werte zurückgeben:

|Problem|Zurück|
|-----------|------------|
|*X* < 0|NaN|
|*X* ±0 =|-UNENDLICH|
|*X* = 1|+0|
|+UNENDLICH|+INFINITY|
|NaN|NaN|
|Domänenfehler|NaN|
|pole-Fehler|-HUGE_VAL, -HUGE_VALF, oder -HUGE_VALL|

Fehler werden gemäß der Angaben in [_matherr](matherr.md) gemeldet.

## <a name="remarks"></a>Hinweise

Wenn x eine ganze Zahl ist, gibt diese Funktion im Wesentlichen den nullbasierten Index des höchstwertigen 1 Bit der *x*.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**log2**, **log2f**, **log2l**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
