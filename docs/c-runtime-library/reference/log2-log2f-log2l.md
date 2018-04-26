---
title: log2, log2f, log2l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
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
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ddde058c61bfbe83013111e3376a84bd463cd650
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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
