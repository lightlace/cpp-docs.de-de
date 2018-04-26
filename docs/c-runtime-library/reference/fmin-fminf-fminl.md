---
title: Fmin, Fminf, Fminl | Microsoft Docs
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
- fmin
- fminf
- fminl
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
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3de46ba0a8d550d961fd05527b49a68a1518c50a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

Bei erfolgreicher Ausführung gibt die kleinere von *x* oder *y*.

|Eingabe|Ergebnis|
|-----------|------------|
|*X* ist "NaN"|*y*|
|*y* ist "NaN"|*w*|
|*X* und *y* sind "NaN"|NaN|

Die Funktion führt nicht dazu, dass [_matherr](matherr.md) um aufgerufen werden, dazu führen, dass alle Gleitkommaausnahmen, oder ändern Sie den Wert der **Errno**.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Fmin** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Fmin** immer Double und gibt eine **doppelte**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**Fmin**, **Fminf**, **Fminl**|C: \<math.h><br />C++: \<math.h> oder \<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[fmax, fmaxf, fmaxl](fmax-fmaxf-fmaxl.md)<br/>
