---
title: _finite, _finitef
ms.date: 04/05/2018
apiname:
- _finite
- _finitef
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
- finite
- _finite
- _finitef
- math/_finite
- math/_finitef
- float/_finite
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
ms.openlocfilehash: 7b1bce6f1b2da77ed9de255f49dd8d0160e33e31
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431662"
---
# <a name="finite-finitef"></a>_finite, _finitef

Bestimmt, ob ein Gleitkommawert endlich ist.

## <a name="syntax"></a>Syntax

```C
int _finite(
   double x
);

int _finitef(
   float x
); /* x64 and ARM/ARM64 only */
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der zu testende Gleitkommawert.

## <a name="return-value"></a>Rückgabewert

Beide **_finite** und **_finitef** einen Wert ungleich NULL zurück, wenn das Argument *x* ist endlich ist, d.h., wenn -INF < *x* < + INF. 0 (null), wenn das Argument unendlich oder ein NaN-Wert ist.

## <a name="remarks"></a>Hinweise

Die **_finite** und **_finitef** Funktionen sind Microsoft-spezifisch. Die **_finitef** -Funktion ist nur verfügbar, wenn für X86, ARM und ARM64-Plattformen kompiliert.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|--------------|---------------------------|-------------------------------|
|**_finite**|\<float.h> or \<math.h>|\<float.h>, \<math.h>, \<cfloat>, or \<cmath>|
|**_finitef**|\<math.h>|\<math.h> or \<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
