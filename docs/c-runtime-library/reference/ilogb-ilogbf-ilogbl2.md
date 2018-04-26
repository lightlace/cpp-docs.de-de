---
title: ilogb, ilogbf, ilogbl2 | Microsoft-Dokumentation
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
- ilogb
- ilogbf
- ilogbl
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
- ilogb
- ilogbf
- ilogbl
- math/ilogb
- math/ilogbf
- math/ilogbl
helpviewer_keywords:
- ilogb function
- ilogbf function
- ilogbl function
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dc15d09b2e2ff79771b2be4250ea1ea770a02f31
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb, ilogbf, ilogbl

Ruft eine Ganzzahl ab, die den unausgewogenen Basis-2-Exponenten des angegebenen Werts darstellt.

## <a name="syntax"></a>Syntax

```C
int ilogb(
   double x
);

int ilogb(
   float x
); //C++ only

int ilogb(
   long double x
); //C++ only

int ilogbf(
   float x
);

int ilogbl(
   long double x
);

```

### <a name="parameters"></a>Parameter

*w*<br/>
Der angegebene Wert.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg zurück der Exponent zur Basis-2 *x* als eine signierte **Int** Wert.

Andernfalls gibt er die folgenden, in \<math.h> definierten Werte zurück:

|Eingabe|Ergebnis|
|-----------|------------|
|±0|FP_ILOGB0|
|±INF ±nan unbestimmtes|FP_ILOGBNAN|

Fehler werden gemäß den Angaben in [_matherr](matherr.md) gemeldet.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Ilogb** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Ilogb** immer Double und gibt eine **doppelte**.

Das Aufrufen dieser Funktion ist ähnlich wie beim Aufrufen der entsprechenden **Logb** -Funktion, und klicken Sie dann den Rückgabewert in die Umwandlung **Int**.

## <a name="requirements"></a>Anforderungen

|Routine|C-Header|C++-Header|
|-------------|--------------|------------------|
|**Ilogb**, **Ilogbf**, **Ilogbl**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[frexp](frexp.md)<br/>
[logb, logbf, logbl, _logb, _logbf](logb-logbf-logbl-logb-logbf.md)<br/>
