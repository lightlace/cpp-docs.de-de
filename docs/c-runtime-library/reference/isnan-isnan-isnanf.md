---
title: isnan, _isnan, _isnanf | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- NAN (not a number)
- _isnan function
- IEEE floating-point representation
- Not a Number (NANs)
- isnan function
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6b8552f59bc0d49ebae0d4a534225af5d9f5facb
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

In C die **Isnan** Makros und die **_isnan** und **_isnanf** Funktionen geben einen Wert ungleich NULL zurück, wenn das Argument *x* ist ein NAN ist andernfalls sie Geben Sie 0 zurück.

In C++ wird die **Isnan** Vorlagenfunktionen Return **"true"** Wenn das Argument *x* ist ein NAN; andernfalls geben sie zurück **"false"**.

## <a name="remarks"></a>Hinweise

Das C **Isnan** Makros und die **_isnan** und **_isnanf** Funktionen testen Gleitkommawert *x*, einen Wert ungleich NULL zurückgeben, wenn *x* ist keine Zahl (NAN)-Wert. Ein NAN-Wert wird generiert, wenn das Ergebnis einer Gleitkommaoperation nicht im IEEE-754 Gleitkommaformat für den angegebenen Typ dargestellt werden kann. Informationen darüber, wie ein NAN für die Ausgabe dargestellt wird, erhalten Sie unter [printf](printf-printf-l-wprintf-wprintf-l.md).

Beim Kompilieren als C++, die **Isnan** Makro ist nicht definiert, und ein **Isnan** Vorlagenfunktion wird stattdessen definiert. Es gibt einen Wert vom Typ **Bool** kein ganze Zahl.

Die **_isnan** und **_isnanf** Funktionen sind Microsoft-spezifisch. Die **_isnanf** Funktion ist nur verfügbar, wenn für X64 kompiliert.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|-------------|---------------------------|-------------------------------|
|**IsNaN**, **_isnanf**|\<math.h>|\<math.h> oder \<cmath>|
|**_isnan**|\<float.h>|\<float.h> oder \<cfloat>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[_finite, _finitef](finite-finitef.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
