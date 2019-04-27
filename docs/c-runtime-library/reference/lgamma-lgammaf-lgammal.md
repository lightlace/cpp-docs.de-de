---
title: lgamma, lgammaf, lgammal
ms.date: 04/05/2018
apiname:
- lgamma
- lgammaf
- lgammal
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
- lgamma
- lgammaf
- lgammal
- math/lgamma
- math/lgammaf
- math/lgammal
helpviewer_keywords:
- lgamma function
- lgammal function
- lgammaf function
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
ms.openlocfilehash: 43ce1599ab9161b9fadf5643ddd2ec739ab2d8b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157283"
---
# <a name="lgamma-lgammaf-lgammal"></a>lgamma, lgammaf, lgammal

Bestimmt den natürlichen Logarithmus des absoluten Werts der Gammafunktion des angegebenen Werts.

## <a name="syntax"></a>Syntax

```C
double lgamma( double x );
float lgammaf( float x );
long double lgammal( long double x );
```

```cpp
float lgamma( float x ); //C++ only
long double lgamma( long double x ); //C++ only
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der zu berechnende Wert.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg zurückgegeben. der natürliche Logarithmus des absoluten Werts der Gammafunktion des *x*.

|Problem|Zurück|
|-----------|------------|
|*x* = NaN|NaN|
|*x* = ±0|+INFINITY|
|*X*= negative ganze Zahl|+INFINITY|
|±INFINITY|+INFINITY|
|pole-Fehler|+HUGE_VAL, +HUGE_VALF, oder +HUGE_VALL|
|Überlaufbereichsfehler|±HUGE_VAL ±HUGE_VALF oder ±HUGE_VALL|

Fehler werden wie in [_matherr](matherr.md) angegeben gemeldet.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Lgamma** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Lgamma** immer Double und gibt eine **doppelte**.

Wenn x eine rationale Zahl ist, gibt diese Funktion den Logarithmus der Fakultät von (X - 1) zurück.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**lgamma**, **lgammaf**, **lgammal**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[tgamma, tgammaf, tgammal](tgamma-tgammaf-tgammal.md)<br/>
