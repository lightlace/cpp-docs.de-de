---
title: logb, logbf, logbl, _logb, _logbf
ms.date: 04/05/2018
apiname:
- logb
- _logb
- _logbl
- logbf
- logbl
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
- logb
- logbl
- _logb
- _logbf
- logbf
helpviewer_keywords:
- _logbf function
- mantissas, floating-point variables
- logbf function
- _logb function
- exponent, floating-point numbers
- logbl function
- logb function
- floating-point functions
- floating-point functions, mantissa and exponent
- exponents and mantissas
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
ms.openlocfilehash: 9f598eedaf30b1f2a1858129e648a117355d112e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466286"
---
# <a name="logb-logbf-logbl-logb-logbf"></a>logb, logbf, logbl, _logb, _logbf

Extrahiert den Exponentenwert eines Gleitkommaarguments.

## <a name="syntax"></a>Syntax

```C
double logb(
   double x
);
float logb(
   float x
); // C++ only
long double logb(
   long double x
); // C++ only
float logbf(
   float x
);
long double logbl(
   long double x
);
double _logb(
   double x
);
float _logbf(
   float x
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Ein Gleitkommawert.

## <a name="return-value"></a>Rückgabewert

**Logb** gibt den zufälligen Exponentenwert von *x* als eine Ganzzahl mit Vorzeichen als Gleitkommawert dargestellt.

## <a name="remarks"></a>Hinweise

Die **Logb** -Funktionen extrahieren den Exponentialwert des gleitkommaarguments *x*, als dass *x* mit unbegrenztem Bereich dargestellt würde. Wenn das Argument *x* ist denormalisiert, es wird behandelt, als ob er normalisiert wurden.

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Logb** verwenden und zurückgeben **"float"** oder **lange** **doppelte** Werte. In einem C-Programm **Logb** immer Double und gibt eine **doppelte**.

|Eingabe|SEH-Ausnahme|Matherr-Ausnahme|
|-----------|-------------------|-----------------------|
|± QNAN,IND|Keiner|_DOMAIN|
|± 0|ZERODIVIDE|_SING|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_logb**|\<float.h>|
|**Logb**, **Logbf**, **Logbl**, **_logbf**|\<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[frexp](frexp.md)<br/>
