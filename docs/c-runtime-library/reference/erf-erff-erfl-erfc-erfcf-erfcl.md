---
title: erf, erff, erfl, erfc, erfcf, erfcl
ms.date: 01/31/2019
apiname:
- erff
- erfl
- erf
- erfc
- erfcf
- erfcl
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
- erfc
- erfcf
- erfcl
helpviewer_keywords:
- erfl function
- erff function
- erf function
- erfcl function
- erfcf function
- erfc function
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
ms.openlocfilehash: 4270d8366686ea282a4dd37741d9f8e37991b88f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62289200"
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

Die **Erf** -Funktionen berechnen die Gauß-Fehlerfunktion von *x*, die als definiert ist:

![Die Fehlerfunktion von x](media/crt_erf_formula.PNG "die Fehlerfunktion von x")

Die komplementäre Gauß-Fehlerfunktion ist definiert als 1 - erf(x). Die **Erf** Funktionen geben einen Wert im Bereich-1,0 1,0 zurück. Es gibt keine Fehlerrückgabe. Die **Erfc** Funktionen geben einen Wert im Bereich von 0 bis 2 zurück. Wenn *x* ist zu groß für **Erfc**, **Errno** Variable nastaven NA hodnotu **ERANGE**.

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Erf** und **Erfc** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Erf** und **Erfc** immer annehmen und Zurückgeben einer **doppelte**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**erf**, **erff**, **erfl**, **erfc**, **erfcf**, **erfcl**|\<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
