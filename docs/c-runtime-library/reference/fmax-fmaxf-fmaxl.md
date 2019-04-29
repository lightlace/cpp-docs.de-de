---
title: fmax, fmaxf, fmaxl
ms.date: 04/05/2018
apiname:
- fmax
- fmaxf
- fmaxl
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
- fmax
- fmaxf
- fmaxl
- math/fmax
- math/fmaxf
- math/fmaxl
helpviewer_keywords:
- fmax function
- fmaxf function
- fmaxl function
ms.assetid: a773ccf7-495e-4a9a-8c6d-dfb53e341e35
ms.openlocfilehash: 371d53257427f2235048807968c82fec1b8bf699
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333430"
---
# <a name="fmax-fmaxf-fmaxl"></a>fmax, fmaxf, fmaxl

Bestimmen Sie den größeren von zwei angegebenen numerischen Werten.

## <a name="syntax"></a>Syntax

```C
double fmax(
   double x,
   double y
);

float fmax(
   float x,
   float y
); //C++ only

long double fmax(
   long double x,
   long double y
); //C++ only

float fmaxf(
   float x,
   float y
);

long double fmaxl(
   long double x,
   long double y
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der erste zu vergleichende Wert.

*y*<br/>
Der zweite zu vergleichende Wert.

## <a name="return-value"></a>Rückgabewert

Bei erfolgreicher Ausführung gibt die größere von *x* oder *y*. Der zurückgegebene Wert ist genau und erfordert keinerlei Rundung.

Andernfalls wird möglicherweise einer der folgenden Werte zurückgeben:

|Problem|Zurück|
|-----------|------------|
|*x* = NaN|*y*|
|*y* = NaN|*w*|
|*X* und *y* = NaN|NaN|

Diese Funktion verwendet nicht die in [_matherr](matherr.md) angegebenen Fehler.

## <a name="remarks"></a>Hinweise

Da C++ Überladungen zulässt, können Sie Überladungen von fmax aufrufen, die float- und long double-Typen annehmen und zurückgeben. In einem C-Programm verwendet fmax immer einen double-Typen und gibt auch einen zurück.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**fmax**, **fmaxf**, **fmaxl**|\<math.h>|\<cmath> oder \<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fmin, fminf, fminl](fmin-fminf-fminl.md)<br/>
