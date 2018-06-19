---
title: tgamma, tgammaf, tgammal | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- tgamma
- tgammaf
- tgammal
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
- tgamma
- tgammaf
- tgammal
- math/tgamma
- math/tgammaf
- math/tgammal
dev_langs:
- C++
helpviewer_keywords:
- tgamma function
- tgammaf function
- tgammal function
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7861b297646f4a704134e0d874fad8c924a7ebc8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409874"
---
# <a name="tgamma-tgammaf-tgammal"></a>tgamma, tgammaf, tgammal

Bestimmt die Gammafunktion des angegebenen Werts.

## <a name="syntax"></a>Syntax

```C
double tgamma(
   double x
);

float tgamma(
   float x
); //C++ only

long double tgamma(
   long double x
); //C++ only

float tgammaf(
   float x
);

long double tgammal(
   long double x
);

```

### <a name="parameters"></a>Parameter

*w*<br/>
Der Wert, dessen Gamma gefunden werden soll.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg gibt der Gammawert *x*.

Ein Bereichsfehler kann auftreten, wenn die Größe der *x* ist zu groß oder zu klein für den Datentyp. Ein Domänenfehler oder Bereichsfehler kann auftreten, wenn *x* < = 0.

|Problem|Zurück|
|-----------|------------|
|x = ±0|±INFINITY|
|x = negative ganze Zahl|NaN|
|X = - UNENDLICH|NaN|
|x = +INFINITY|+INFINITY|
|x = NaN|NaN|
|Domänenfehler|NaN|
|pole-Fehler|±HUGE_VAL, ±HUGE_VALF oder ±HUGE_VALL|
|Überlaufbereichsfehler|±HUGE_VAL, ±HUGE_VALF oder ±HUGE_VALL|
|Unterlaufbereichsfehler|Richtiger Wert nach dem Runden|

Fehler werden gemäß der Angaben in [_matherr](matherr.md) gemeldet.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Tgamma** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Tgamma** immer Double und gibt eine **doppelte**.

Wenn x eine natürliche Zahl ist, gibt diese Funktion die Fakultät von (x-1) zurück.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**Tgamma**, **Tgammaf**, **Tgammal**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[lgamma, lgammaf, lgammal](lgamma-lgammaf-lgammal.md)<br/>
