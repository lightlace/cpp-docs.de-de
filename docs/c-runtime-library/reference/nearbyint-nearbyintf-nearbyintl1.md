---
title: nearbyint, nearbyintf, nearbyintl
ms.date: 04/05/2018
apiname:
- nearbyint
- nearbyintf
- nerabyintl
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
- nearbyint
- nearbyintf
- nearbyintl
- math/nearbyint
- math/narbyintf
- math/narbyintl
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
ms.openlocfilehash: 4a36bddb28db9fb4c5809432dfaef9ca3ece4328
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668311"
---
# <a name="nearbyint-nearbyintf-nearbyintl"></a>nearbyint, nearbyintf, nearbyintl

Rundet den angegebenen Gleitkommawert auf eine ganze Zahl und gibt diesen Wert in einem Gleitkommaformat zurück.

## <a name="syntax"></a>Syntax

```C
double nearbyint( double x );
float nearbyintf( float x );
long double nearbyintl( long double x );
```

```cpp
float nearbyint( float x ); //C++ only
long double nearbyint( long double x ); //C++ only
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der zu rundende Wert.

## <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird *x*, gerundet auf die nächste ganze Zahl, mit dem aktuellen Rundungsformat, von gemeldeten [Fegetround](fegetround-fesetround2.md). Andernfalls gibt die Funktion möglicherweise einen der folgenden Werte zurück:

|Problem|Zurück|
|-----------|------------|
|*X* ±INFINITY =|±Infinity, unverändert|
|*X* ±0 =|±0, unverändert|
|*X* = NaN|NaN|

Fehler werden nicht gemeldet, über [_matherr](matherr.md), genauer gesagt, diese Funktion meldet keine **FE_INEXACT** Ausnahmen.

## <a name="remarks"></a>Hinweise

Der Hauptunterschied zwischen dieser Funktion und [Rint](rint-rintf-rintl.md) besteht darin, dass diese Funktion keine ungenaue Gleitkommaausnahme auslöst.

Da die maximalen Gleitkommawerte genaue ganze Zahlen sind, überläuft diese Funktion nie von selbst. Stattdessen ist es möglich, dass der Rückgabewert je nach Version der verwendeten Funktion von der Ausgabe überlaufen wird.

Da C++ das Überladen zulässt, können Sie Überladungen von aufrufen können **Nearbyint** verwenden und zurückgeben **"float"** oder **lange** **doppelte** Parameter. In einem C-Programm **Nearbyint** immer zwei double-Werten und gibt einen doppelten Wert zurück.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**Nearbyint**, **Nearbyintf**, **Nearbyintl**|\<math.h>|\<cmath> oder \<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[Mathematische Unterstützung und gleitkommaunterstützung](../floating-point-support.md)<br/>
