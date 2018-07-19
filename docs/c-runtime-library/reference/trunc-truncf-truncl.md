---
title: trunc, truncf, truncl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- trunc
- truncf
- truncl
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
- trunc
- truncf
- truncl
- math/trunc
- math/truncf
- math/truncl
dev_langs:
- C++
helpviewer_keywords:
- trunc function
- truncf function
- truncl function
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67c179065a6b2c6fc10a4ba6ba87868c8306a2aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409458"
---
# <a name="trunc-truncf-truncl"></a>trunc, truncf, truncl

Bestimmt die nächste ganze Zahl, die kleiner oder gleich dem angegebenen Gleitkommawert ist.

## <a name="syntax"></a>Syntax

```C
double trunc( double x );
float trunc( float x ); //C++ only
long double truncl( long double x );
```

```cpp
long double trunc( long double x ); //C++ only
float trunc( float x ); //C++ only
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der abzuschneidende Wert.

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall gibt einen ganzzahligen Wert des *x*in Richtung 0 (null) gerundet.

Andernfalls wird möglicherweise einer der folgenden Werte zurückgeben:

|Problem|Zurück|
|-----------|------------|
|*X* = ±INFINITY|w|
|*X* = ±0|w|
|*X* = "NaN"|NaN|

Fehler werden gemäß der Angaben in [_matherr](matherr.md) gemeldet.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Trunc** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Trunc** immer Double und gibt eine **doppelte**.

Da die größten Gleitkommawerte exakte ganze Zahlen sind, wird diese Funktion nicht eigenständig überlaufen. Sie können diese Funktion jedoch möglicherweise bei der Rückgabe eines Werts in einen ganzzahligen Typ zum Überlaufen bringen.

Sie können auch abrunden, indem Sie Gleitkommazahlen implizit in ganzzahlige konvertieren. Dies ist jedoch nur für die Werte möglich, die im Zieltyp gespeichert werden können.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**Trunc**, **Truncf**, **Truncl**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[floor, floorf, floorl](floor-floorf-floorl.md)<br/>
[ceil, ceilf, ceill](ceil-ceilf-ceill.md)<br/>
[round, roundf, roundl](round-roundf-roundl.md)<br/>
