---
title: log1p, log1pf, log1pl2
ms.date: 04/05/2018
apiname:
- log1p
- log1pf
- log1pl
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
ms.openlocfilehash: 2ac864d7e28823c95b0202c0a8f2454d03c64aff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62285985"
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

Wenn erfolgreich, wird der natürliche (Basis*e*) melden Sie sich von (*x* + 1).

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

Die **Errno** Wert wird auf ERANGE festgelegt, wenn *x* =-1. Die **Errno** Wert wird festgelegt, um **EDOM** Wenn *x* < -1.

## <a name="remarks"></a>Hinweise

Die **log1p** Funktionen sind möglicherweise genauer als `log(x + 1)` beim *x* nahe 0 ist.

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **log1p** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **log1p** immer Double und gibt eine **doppelte**.

Wenn *x* eine natürliche Zahl ist, wird diese Funktion gibt den Logarithmus der Fakultät von (*x* - 1).

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**log1p**, **log1pf**, **log1pl**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[log2, log2f, log2l](log2-log2f-log2l.md)<br/>
[log, logf, log10, log10f](log-logf-log10-log10f.md)<br/>
