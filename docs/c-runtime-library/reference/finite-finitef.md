---
title: isfinite, _finite, _finitef
ms.date: 01/31/2019
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- isfinite
- finite
- _finite
- _finitef
- math/isfinite
- math/_finite
- math/_finitef
- float/_finite
helpviewer_keywords:
- finite function
- _finite function
- _finitef function
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
ms.openlocfilehash: d727839521978be66c3dc9ee173ee2ba0a567445
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333715"
---
# <a name="isfinite-finite-finitef"></a>isfinite, _finite, _finitef

Bestimmt, ob ein Gleitkommawert endlich ist.

## <a name="syntax"></a>Syntax

```C
int isfinite(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isfinite(
   FloatingType x
) throw(); /* C++-only template function */

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

Die `isfinite` Makro und die `_finite` und `_finitef` Funktionen geben einen Wert ungleich NULL zurück, wenn *x* entweder mit normaler oder subnormal mit endlicher Wert. Sie geben die 0, wenn das Argument unendlich ist oder ein NaN-Wert zurück. Die C++-Inline-Vorlagenfunktion `isfinite` verhält sich genauso, gibt jedoch **"true"** oder **"false"**.

## <a name="remarks"></a>Hinweise

`isfinite` ist ein Makro, wenn als C, und eine Vorlage Inlinefunktion beim Kompilieren als C++ kompiliert. Die `_finite` und `_finitef` Funktionen sind Microsoft-spezifisch. Die Funktion `_finitef` ist nur verfügbar, wenn sie für x86, ARM- oder ARM64-Plattformen kompiliert wurde.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|--------------|---------------------------|-------------------------------|
|`_finite`|\<float.h> or \<math.h>|\<float.h>, \<math.h>, \<cfloat>, or \<cmath>|
|`isfinite`, `_finitef`|\<math.h>|\<math.h> or \<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
