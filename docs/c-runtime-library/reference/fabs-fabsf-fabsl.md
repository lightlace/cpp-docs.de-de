---
title: fabs, fabsf, fabsl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fabsf
- fabs
- fabsl
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
- fabs
- fabsf
- fabsl
- "math\fabs"
- "math\fabsf"
- "math\fabsl"
dev_langs:
- C++
helpviewer_keywords:
- absolute values
- fabsf function
- calculating absolute values
- fabs function
- fabsl function
ms.assetid: 23bca210-f408-4f5e-b46b-0ccaaec31e36
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 95f34d81045aef90832a1d05090c548c1bf27dec
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

Die **Fabs** Funktionen geben den absoluten Wert des Arguments zurück *x*. Es gibt keine Fehlerrückgabe.

|Eingabe|SEH-Ausnahme|Matherr-Ausnahme|
|-----------|-------------------|-----------------------|
|± QNAN,IND|Keine|_DOMAIN|

## <a name="remarks"></a>Hinweise

C++ das Überladen zulässt, sodass Sie Überladungen von aufrufen können **Fabs** Wenn Sie enthalten die \<Cmath > Header. In einem C-Programm **Fabs** immer Double und gibt eine **doppelte**.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher C-Header|Erforderlicher C++-Header|
|--------------|-----------------------|---------------------------|
|**Fabs**, **Fabsf**, **Fabsl**|\<math.h>|\<cmath> oder \<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [abs](abs-labs-llabs-abs64.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[abs, labs, llabs, _abs64](abs-labs-llabs-abs64.md)<br/>
[_cabs](cabs.md)<br/>
