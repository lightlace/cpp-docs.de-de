---
title: fpclassify
ms.date: 04/05/2018
apiname:
- fpclassify
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
apitype: HeaderDef
f1_keywords:
- fpclassify
- math/fpclassify
helpviewer_keywords:
- fpclassify macro
- fpclassify function
ms.assetid: bf549499-7ff9-4a58-8692-f2d1cb6bab81
ms.openlocfilehash: 626e356cf61415e4f8212a8a12d90a72fe4576bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613875"
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

**Fpclassify** gibt einen ganzzahligen Wert, der die gleitkommaklasse des Arguments angibt *x*. Diese Tabelle zeigt die möglichen Rückgabewerte **Fpclassify**, definiert in \<math.h >.

|Wert|Beschreibung|
|-----------|-----------------|
|**FP_NAN**|Ein stiller, signalisierender oder unbestimmter NaN|
|**FP_INFINITE**|Eine positive oder negative Unendlichkeit|
|**FP_NORMAL**|Ein positiver oder negativer ungleich null normalisierter Wert|
|**FP_SUBNORMAL**|Ein positiver oder negativer denormalisierter Wert|
|**FP_ZERO**|Ein positiver oder negativer Nullwert|

## <a name="remarks"></a>Hinweise

In C **Fpclassify** ist ein Makro; in C++ **Fpclassify** ist eine Funktion überladen, mithilfe der Argumenttypen **"float"**, **doppelte**, oder **lange** **doppelte**. In beiden Fällen hängt der zurückgegebene Wert vom tatsächlichen Typ des Argumentausdrucks ab, und nicht von einer Zwischendarstellung. Z. B. ein normaler **doppelte** oder **lange** **doppelte** Wert wird unendlich, denormal oder NULL-Wert, bei der Konvertierung in kann ein **"float"**.

## <a name="requirements"></a>Anforderungen

|Funktion/Makro|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> oder \<cmath>|

Die **Fpclassify** Makro und **Fpclassify** Funktionen entsprechen den ISO C99 und C ++ 11-Spezifikationen. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
