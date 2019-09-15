---
title: log1p, log1pf, log1pl2
ms.date: 04/05/2018
api_name:
- log1p
- log1pf
- log1pl
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
- log1p
- log1pf
- log1pl
- math/log1p
- math/log1pf
- math/log1pl
helpviewer_keywords:
- log1p function
- log1pf function
- log1pl function
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
ms.openlocfilehash: aad6675a832e1715c505026fe11ffe77f1f6d275
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953217"
---
# <a name="log1p-log1pf-log1pl"></a>log1p, log1pf, log1pl

Berechnet den natürlichen Logarithmus von 1 plus den angegebenen Ausdruck.

## <a name="syntax"></a>Syntax

```C
double log1p(
   double x
);

float log1p(
   float x
); //C++ only

long double log1p(
   long double x
); //C++ only

float log1pf(
   float x
);

long double log1pl(
   long double x
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Das Gleitkommaargument.

## <a name="return-value"></a>Rückgabewert

Bei erfolgreicher Ausführung wird das natürliche Protokoll (Base-*e*) von (*x* + 1) zurückgegeben.

Andernfalls wird möglicherweise einer der folgenden Werte zurückgeben:

|Eingabe|Ergebnis|SEH-Ausnahme|errno|
|-----------|------------|-------------------|-----------|
|+inf|+inf|||
|Abbrüche|Identisch mit der Eingabe|UNDERFLOW||
|±0|Identisch mit der Eingabe|||
|-1|-inf|DIVBYZERO|ERANGE|
|< -1|nan|INVALID|EDOM|
|-inf|nan|INVALID|EDOM|
|±SNaN|Identisch mit der Eingabe|INVALID||
|±QNaN, indefinite|Identisch mit der Eingabe|||

Der **errno** -Wert ist auf ERANGE festgelegt, wenn *x* =-1. Der **errno** -Wert ist auf **Edom** festgelegt, wenn *x* <-1.

## <a name="remarks"></a>Hinweise

Die **log1p** -Funktionen sind möglicherweise präziser als `log(x + 1)` die Verwendung von, wenn *x* nahe 0 (null) ist.

Da C++ das überladen zulässt, können Sie über Ladungen von **log1p** aufzurufen, die **float** -und **Long** **Double** -Typen annehmen und zurückgeben. In einem C-Programm nimmt **log1p** immer einen **Double**-Wert an und gibt ihn zurück.

Wenn *x* eine natürliche Zahl ist, gibt diese Funktion den Logarithmus der Fakultät von (*x* -1) zurück.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**log1p**, **log1pf**, **log1pl**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
