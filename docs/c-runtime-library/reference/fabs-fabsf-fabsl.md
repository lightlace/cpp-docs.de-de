---
title: fabs, fabsf, fabsl
ms.date: 04/05/2018
api_name:
- fabsf
- fabs
- fabsl
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
- fabs
- fabsf
- fabsl
- "math\fabs"
- "math\fabsf"
- "math\fabsl"
helpviewer_keywords:
- absolute values
- fabsf function
- calculating absolute values
- fabs function
- fabsl function
ms.assetid: 23bca210-f408-4f5e-b46b-0ccaaec31e36
ms.openlocfilehash: 155b0e4ced7eb4ea0ade5445a62fc385f0c157e9
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941495"
---
# <a name="fabs-fabsf-fabsl"></a>fabs, fabsf, fabsl

Berechnet den absoluten Wert des Gleitkommaarguments.

## <a name="syntax"></a>Syntax

```C
double fabs(
   double x
);
float fabs(
   float x
); // C++ only
long double fabs(
   long double x
); // C++ only
float fabsf(
   float x
);
long double fabsl(
   long double x
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkommawert.

## <a name="return-value"></a>Rückgabewert

Die **Fabs** -Funktionen geben den absoluten Wert des Arguments *x*zurück. Es gibt keine Fehlerrückgabe.

|Eingabe|SEH-Ausnahme|Matherr-Ausnahme|
|-----------|-------------------|-----------------------|
|± QNAN,IND|none|_DOMAIN|

## <a name="remarks"></a>Hinweise

C++ermöglicht überladen, sodass Sie über Ladungen von **Fabs** aufzurufen können, wenn Sie \<den cmath-> Header einschließen. In einem C-Programm nimmt **Fabs** immer einen **Double**-Wert an und gibt ihn zurück.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher C-Header|Erforderlicher C++-Header|
|--------------|-----------------------|---------------------------|
|**fabs**, **fabsf**, **fabsl**|\<math.h>|\<cmath> oder \<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [abs](abs-labs-llabs-abs64.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[_cabs](cabs.md)<br/>
