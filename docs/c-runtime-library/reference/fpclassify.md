---
title: fpclassify | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da55cb87804d178d5a305ed466aa498de4bc1ee5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398431"
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

**Fpclassify** gibt einen ganzzahligen Wert, der die gleitkommaklasse des Arguments angibt *x*. Diese Tabelle zeigt die möglichen Rückgabewerte **Fpclassify**in definierte \<math.h >.

|Wert|Beschreibung|
|-----------|-----------------|
|**FP_NAN**|Ein stiller, signalisierender oder unbestimmter NaN|
|**FP_INFINITE**|Eine positive oder negative Unendlichkeit|
|**FP_NORMAL**|Ein positiver oder negativer ungleich null normalisierter Wert|
|**FP_SUBNORMAL**|Ein positiver oder negativer denormalisierter Wert|
|**FP_ZERO**|Ein positiver oder negativer Nullwert|

## <a name="remarks"></a>Hinweise

In C **Fpclassify** ist ein Makro; in C++ **Fpclassify** ist eine Funktion überladen mithilfe von Argumenttypen **"float"**, **doppelte**, oder **lange** **doppelte**. In beiden Fällen hängt der zurückgegebene Wert vom tatsächlichen Typ des Argumentausdrucks ab, und nicht von einer Zwischendarstellung. Z. B. ein normaler **doppelte** oder **lange** **doppelte** Wert kann unendlich, denormal werden bzw. 0 (null) Wert bei der Konvertierung in einen **"float"**.

## <a name="requirements"></a>Anforderungen

|Funktion/Makro|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|---------------------|---------------------------|-------------------------------|
|**fpclassify**|\<math.h>|\<math.h> oder \<cmath>|

Die **Fpclassify** Makro und **Fpclassify** Funktionen die ISO C99 und C ++ 11-Spezifikationen entsprechen. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
