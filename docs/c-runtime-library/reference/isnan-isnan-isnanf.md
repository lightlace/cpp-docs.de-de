---
title: isnan, _isnan, _isnanf
ms.date: 01/31/2019
apiname:
- _isnan
- _isnanf
- isnan
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
- _isnan
- isnan
- math/isnan
- math/_isnan
- math/_isnanf
- _isnanf
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
ms.openlocfilehash: 8a907dd33803cebd7bc5d71789834d115333b6a0
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703089"
---
# <a name="isnan-isnan-isnanf"></a>isnan, _isnan, _isnanf

Testet, ob ein Gleitkommawert keine Zahl ist (NAN).

## <a name="syntax"></a>Syntax

```C
int isnan(
   /* floating-point */ x
); /* C-only macro */

int _isnan(
   double x
);

int _isnanf(
   float x
); /* x64 only */

template <class T>
bool isnan(
   T x
) throw(); /* C++ only */
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der zu testende Gleitkommawert.

## <a name="return-value"></a>Rückgabewert

In C die **Isnan** Makro und die **_isnan** und **_isnanf** Funktionen geben einen Wert ungleich NULL zurück, wenn das Argument *x* ein NaN ist; andernfalls sie Gibt 0 zurück.

In C++ die **Isnan** Vorlagenfunktion gibt **"true"** Wenn das Argument *x* ein NaN ist; andernfalls **"false"**.

## <a name="remarks"></a>Hinweise

Da ein NaN-Wert nicht als übereinstimmend mit anderen NaN-Wert vergleichen, müssen Sie eine der folgenden Funktionen oder Makros verwenden, um eine zu erkennen. Ein NaN-Wert wird generiert, wenn das Ergebnis einer Gleitkommaoperation nicht im IEEE-754 Gleitkommaformat für den angegebenen Typ dargestellt werden kann. Weitere Informationen dazu, wie ein NaN-Wert für die Ausgabe dargestellt wird, finden Sie unter [Printf](printf-printf-l-wprintf-wprintf-l.md).

Wenn als C++ kompiliert die **Isnan** -Makro nicht definiert ist, und ein **Isnan** Vorlagenfunktion stattdessen definiert ist. Verhält sich genauso wie das Makro, sondern gibt einen Wert vom Typ **"bool"** anstelle einer ganzen Zahl.

Die **_isnan** und **_isnanf** Funktionen sind Microsoft-spezifisch. Die **_isnanf** Funktion ist nur verfügbar, wenn für X64 kompiliert.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|-------------|---------------------------|-------------------------------|
|**isnan**, **_isnanf**|\<math.h>|\<math.h> oder \<cmath>|
|**_isnan**|\<float.h>|\<float.h> oder \<cfloat>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnormal](isnormal.md)<br/>
