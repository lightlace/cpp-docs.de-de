---
title: isnormal
ms.date: 01/31/2019
f1_keywords:
- isnormal
- math/isnormal
helpviewer_keywords:
- isnormal function
ms.openlocfilehash: e426fbce71efff1e810a03b8347e7c48aa0d91d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62286439"
---
# <a name="isnormal"></a>isnormal

Bestimmt, ob ein Gleitkommawert ein normaler Wert ist.

## <a name="syntax"></a>Syntax

```C
int isnormal(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isnormal(
   FloatingType x
) throw(); /* C++-only function template */
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der zu testende Gleitkommawert.

## <a name="return-value"></a>Rückgabewert

**Isnormal** gibt einen Wert ungleich Null (**"true"** in C++ Code) Wenn das Argument *x* ist 0 (null), Subnormal, unendlich oder ein NaN-Wert. Andernfalls **Isnormal** gibt 0 zurück (**"false"** in C++ Code).

## <a name="remarks"></a>Hinweise

**Isnormal** ist ein Makro, die beim Kompilieren als C++, und eine Inlinevorlage-Funktion beim Kompilieren als C++.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|--------------|---------------------------|-------------------------------|
|**isnormal**|\<math.h>|\<math.h> or \<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
