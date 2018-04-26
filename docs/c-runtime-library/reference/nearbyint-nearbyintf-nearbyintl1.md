---
title: Nearbyint, Nearbyintf, Nearbyintl | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- nearbyint function
- nearbyintf function
- nearbyintl function
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0aacdeb67e7c467bf6f8719172dfd9771e0cec8d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

Im Erfolgsfall gibt *x*, gerundet auf die nächste ganze Zahl, verwenden das aktuelle Format für die Rundung von gemeldeten [Fegetround](fegetround-fesetround2.md). Andernfalls gibt die Funktion möglicherweise einen der folgenden Werte zurück:

|Problem|Zurück|
|-----------|------------|
|*X* = ±INFINITY|±Infinity, unverändert bleiben sollen|
|*X* = ±0|±0, unverändert bleiben sollen|
|*X* = "NaN"|NaN|

Fehler werden nicht gemeldet, über [_matherr](matherr.md), genauer gesagt, diese Funktion meldet keine **FE_INEXACT** Ausnahmen.

## <a name="remarks"></a>Hinweise

Der Hauptunterschied zwischen dieser Funktion und [Rint](rint-rintf-rintl.md) ist, dass diese Funktion keine ungenau Gleitkommaausnahme ausgelöst wird.

Da die maximalen Gleitkommawerte genaue ganze Zahlen sind, überläuft diese Funktion nie von selbst. Stattdessen ist es möglich, dass der Rückgabewert je nach Version der verwendeten Funktion von der Ausgabe überlaufen wird.

C++ das Überladen zulässt, sodass Sie Überladungen von aufrufen können **Nearbyint** verwenden und zurückgeben **"float"** oder **lange** **doppelte** Parameter. In einem C-Programm **Nearbyint** immer zwei double-Werte und gibt einen double-Wert zurück.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**Nearbyint**, **Nearbyintf**, **Nearbyintl**|\<math.h>|\<cmath> oder \<math.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[Mathematische und gleitkommaunterstützung](../floating-point-support.md)<br/>
