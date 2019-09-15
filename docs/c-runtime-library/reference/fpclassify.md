---
title: fpclassify
ms.date: 04/05/2018
api_name:
- fpclassify
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
api_type:
- HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
ms.openlocfilehash: e9b5aa1f7dc20cc920a51c2c36371eb907469875
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957067"
---
# <a name="fpclassify"></a>fpclassify

Gibt die Gleitkommaklassifizierung des Arguments zurück.

## <a name="syntax"></a>Syntax

```C
int fpclassify(
   /* floating-point */ x
);

int fpclassify(
   float x
); // C++ only

int fpclassify(
   double x
); // C++ only

int fpclassify(
   long double x
); // C++ only
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der zu testende Gleitkommawert.

## <a name="return-value"></a>Rückgabewert

**fpklassifiklassifiziert** gibt einen ganzzahligen Wert zurück, der die Gleit Komma Klasse des Arguments *x*angibt. Diese Tabelle zeigt die möglichen Werte, die von **fpklassifiziert**zurückgegeben \<werden, die in Math. h > definiert sind.

|Wert|Beschreibung|
|-----------|-----------------|
|**FP_NAN**|Ein stiller, signalisierender oder unbestimmter NaN|
|**FP_INFINITE**|Eine positive oder negative Unendlichkeit|
|**FP_NORMAL**|Ein positiver oder negativer ungleich null normalisierter Wert|
|**FP_SUBNORMAL**|Ein positiver oder negativer denormalisierter Wert|
|**FP_ZERO**|Ein positiver oder negativer Nullwert|

## <a name="remarks"></a>Hinweise

In C ist **fpklassifiziert** ein Makro. in C++ist **fpklassifiziert** eine Funktion, die mit den Argument Typen **float**, **Double**oder **Long** **Double**überladen wird. In beiden Fällen hängt der zurückgegebene Wert vom tatsächlichen Typ des Argumentausdrucks ab, und nicht von einer Zwischendarstellung. Beispielsweise kann ein normaler **Double** -oder **Long** **Double** -Wert bei der Konvertierung in einen **float**-Wert unendlich, DENORMAL oder NULL sein.

## <a name="requirements"></a>Anforderungen

|Funktion/Makro|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> oder \<cmath>|

Das **fpklassifiziert** -Makro und die **fpklassifiziert** -Funktionen entsprechen den Spezifikationen ISO C99 und c++ 11. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
