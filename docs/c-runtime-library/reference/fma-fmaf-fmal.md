---
title: fma, fmaf, fmal
ms.date: 04/05/2018
apiname:
- fma
- fmaf
- fmal
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
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
ms.openlocfilehash: f96592e245e443bae2f3334da51cae5572753708
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51517799"
---
# <a name="fma-fmaf-fmal"></a>fma, fmaf, fmal

Multipliziert zwei Werte, addiert einen dritten und rundet das Ergebnis, ohne Genauigkeit aufgrund von vorherigen Rundungen einzubüßen.

## <a name="syntax"></a>Syntax

```C
double fma(
   double x,
   double y,
   double z
);

float fma(
   float  x,
   float  y,
   float z
); //C++ only

long double fma(
   long double  x,
   long double  y,
   long double z
); //C++ only

float fmaf(
   float  x,
   float  y,
   float z
);

long double fmal(
   long double  x,
   long double  y,
   long double z
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der erste zu multiplizierende Wert.

*y*<br/>
Der zweite zu multiplizierende Wert.

*z*<br/>
Der hinzuzufügende Wert.

## <a name="return-value"></a>Rückgabewert

Gibt `(x * y) + z`zurück. Der Rückgabewert wird dann mit dem aktuellen Rundungsformat gerundet.

Andernfalls wird möglicherweise einer der folgenden Werte zurückgeben:

|Problem|Zurück|
|-----------|------------|
|*X* = INFINITY, *y* = 0 oder<br /><br /> *X* = 0, *y* = INFINITY|NaN|
|*X* oder *y* = genaue ± UNENDLICH *z* = INFINITY mit umgekehrtem Vorzeichen|NaN|
|*X* oder *y* = NaN|NaN|
|keine (*x* = 0, *y*= indefinite) und *z* = NaN<br /><br /> keine (*x*= indefinite, *y*= 0) und *z* = NaN|NaN|
|Überlaufbereichsfehler|±HUGE_VAL ±HUGE_VALF oder ±HUGE_VALL|
|Unterlaufbereichsfehler|Richtige Wert nach dem Runden|

Fehler werden gemäß der Angaben in [_matherr](matherr.md) gemeldet.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Fma** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Fma** immer Double und gibt eine **doppelte**.

Diese Funktion berechnet den Wert mit unendlicher Genauigkeit und rundet das endgültige Ergebnis dann.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**FMA**, **Fmaf**, **Fmal**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[remainder, remainderf, remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo, remquof, remquol](remquo-remquof-remquol.md)<br/>
