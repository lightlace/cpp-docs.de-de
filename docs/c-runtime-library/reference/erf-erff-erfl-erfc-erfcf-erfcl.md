---
title: erf, erff, erfl, erfc, erfcf, erfcl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- erff
- erfl
- erf
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
- erfl
- erf
- erff
dev_langs:
- C++
helpviewer_keywords:
- erfl function
- erff function
- erf function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1703b4e352fee798a7b38dd16edf6158cd7f53ea
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="erf-erff-erfl-erfc-erfcf-erfcl"></a>erf, erff, erfl, erfc, erfcf, erfcl

Berechnet die Fehlerfunktion oder die komplementäre Fehlerfunktion eines Werts.

## <a name="syntax"></a>Syntax

```C
double erf(
   double x
);
float erf(
   float x
); // C++ only
long double erf(
   long double x
); // C++ only
float erff(
   float x
);
long double erfl(
   long double x
);
double erfc(
   double x
);
float erfc(
   float x
); // C++ only
long double erfc(
   long double x
); // C++ only
float erfcf(
   float x
);
long double erfcl(
   long double x
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Ein Gleitkommawert.

## <a name="return-value"></a>Rückgabewert

Die **Erf** Funktionen geben die Gauß-Fehlerfunktion von *x*. Die **Erfc** Funktionen geben die komplementäre Gauß-Fehlerfunktion von *x*.

## <a name="remarks"></a>Hinweise

Die **Erf** Funktionen berechnen die Gauß-Fehlerfunktion von *x*, die als definiert ist:

![Die Fehlerfunktion von x](media/crt_erf_formula.PNG "CRT_erf_formula")

Die komplementäre Gauß-Fehlerfunktion ist definiert als 1 - erf(x). Die **Erf** Funktionen geben einen Wert im Bereich-1,0 bis 1,0 zurück. Es gibt keine Fehlerrückgabe. Die **Erfc** -Funktionen geben einen Wert im Bereich von 0 bis 2 zurück. Wenn *x* ist zu groß für **Erfc**, **Errno** Variable wird festgelegt, um **ERANGE**.

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Erf** und **Erfc** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Erf** und **Erfc** immer verwenden und Zurückgeben einer **doppelte**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**Erf**, **Erff**, **Erfl**, **Erfc**, **Erfcf**, **Erfcl**|\<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
