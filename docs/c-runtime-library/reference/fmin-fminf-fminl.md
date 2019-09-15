---
title: fmin, fminf, fminl
ms.date: 04/05/2018
api_name:
- fmin
- fminf
- fminl
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fmin
- fminf
- fminl
- math/fmin
- math/fminf
- math/fminl
helpviewer_keywords:
- fmin function
- fminf function
- fminl function
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
ms.openlocfilehash: df01f2205291920b8c0519db622c93048278beb1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957095"
---
# <a name="fmin-fminf-fminl"></a>fmin, fminf, fminl

Bestimmt den kleineren von zwei angegebenen Werten.

## <a name="syntax"></a>Syntax

```C
double fmin(
   double x,
   double y
);

float fmin(
   float x,
   float y
); //C++ only

long double fmin(
   long double x,
   long double y
); //C++ only

float fminf(
   float x,
   float y
);

long double fminl(
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

Bei erfolgreicher Ausführung wird der kleinere von *x* oder *y*zurückgegeben.

|Eingabe|Ergebnis|
|-----------|------------|
|*x* ist NaN|*y*|
|*y* ist NaN|*w*|
|*x* und *y* sind Nan|NaN|

Die Funktion bewirkt nicht, dass [_matherr](matherr.md) aufgerufen wird, keine Gleit Komma Ausnahmen verursacht oder der Wert von **errno**geändert wird.

## <a name="remarks"></a>Hinweise

Da C++ das überladen zulässt, können Sie über Ladungen von **FMIN** aufzurufen, die **float** -und **Long** **Double** -Typen annehmen und zurückgeben. In einem C-Programm nimmt die **Formatierung immer einen** **Double**-Wert an und gibt diesen zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**fmin**, **fminf**, **fminl**|C: \<math.h><br />C++: \<math.h> oder \<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
