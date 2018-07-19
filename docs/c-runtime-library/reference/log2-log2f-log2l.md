---
title: log2, log2f, log2l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16fb56b1a3aef56e201d469974c5de434a08aa41
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399526"
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

Bei Erfolg gibt log2 zurückgeben *x*.

Andernfalls wird möglicherweise einer der folgenden Werte zurückgeben:

|Problem|Zurück|
|-----------|------------|
|*X* < 0|NaN|
|*X* = ±0|-UNENDLICH|
|*X* = 1|+0|
|+UNENDLICH|+INFINITY|
|NaN|NaN|
|Domänenfehler|NaN|
|pole-Fehler|-HUGE_VAL, -HUGE_VALF, oder -HUGE_VALL|

Fehler werden gemäß der Angaben in [_matherr](matherr.md) gemeldet.

## <a name="remarks"></a>Hinweise

Wenn x eine ganze Zahl ist, gibt diese Funktion im Wesentlichen die nullbasierten Index des das höchstwertige 1 Bit der *x*.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**log2**, **log2f**, **log2l**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[exp2, exp2f, exp2l](exp2-exp2f-exp2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
