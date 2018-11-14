---
title: fdim, fdimf, fdiml
ms.date: 04/05/2018
apiname:
- fdim
- fdimf
- fdiml
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
- fdim
- fdimf
- fdiml
- math/fdim
- math/fdimf
- math/fdiml
helpviewer_keywords:
- fdim function
- fdimf function
- fdiml function
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
ms.openlocfilehash: 263635a32b21b01faa84405ab97bd5518f054ba5
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518176"
---
# <a name="fdim-fdimf-fdiml"></a>fdim, fdimf, fdiml

Bestimmt den positiven Unterschied zwischen den ersten und zweiten Werten.

## <a name="syntax"></a>Syntax

```C
double fdim(
   double x,
   double y
);

float fdim(
   float x,
   float y
); //C++ only

long double fdim(
   long double x,
   long double y
); //C++ only

float fdimf(
   float x,
   float y
);

long double fdiml(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der erste Wert.

*y*<br/>
Der zweite Wert.

## <a name="return-value"></a>Rückgabewert

Gibt den positiven Unterschied zwischen *x* und *y*:

|Rückgabewert|Szenario|
|------------------|--------------|
|x-y|wenn x > y|
|0|wenn x <= y|

Andernfalls wird einer der folgenden Fehler zurückgeben:

|Problem|Zurück|
|-----------|------------|
|Überlaufbereichsfehler|+HUGE_VAL, +HUGE_VALF, oder +HUGE_VALL|
|Unterlaufbereichsfehler|Richtiger Wert (nach dem Runden)|
|*X* oder *y* ist NaN|NaN|

Fehler werden gemäß der Angaben in [_matherr](matherr.md) gemeldet.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Fdim** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Fdim** immer Double und gibt eine **doppelte**.

Diese Funktion entspricht, mit Ausnahme der Behandlung von NaN, `fmax(x - y, 0)`.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**Fdim**, **Fdimf**, **Fdiml**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
