---
title: Fegetround Fesetround | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- fegetround
- fesetround
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fegetround
- fesetround
- fenv/fegetround
- fenv/fesetround
dev_langs:
- C++
helpviewer_keywords:
- fegetround function
- fesetround function
ms.assetid: 596af00b-be2f-4f57-b2f5-460485f9ff0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 137d886d557cbb1fee7db1dd60405b9557bf6bf2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="fegetround-fesetround"></a>fegetround, fesetround

Ruft den aktuellen Gleitkomma-Rundungsmodus ab bzw. legt ihn fest.

## <a name="syntax"></a>Syntax

```C
int fegetround(void);

int fesetround(
   int round_mode
);
```

### <a name="parameters"></a>Parameter

*round_mode*<br/>
Der als eines der Gleitkomma-Rundungsmakros festzulegende Rundungsmodus. Wenn der Wert keinem der Gleitkomma-Rundungsmakros entspricht, wird der Rundungsmodus nicht geändert.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg **Fegetround** gibt den Rundungsmodus als einen der Gleitkomma-rundungsmakrowerte zurück. Ein negativer Wert wird zurückgegeben, wenn der aktuelle Rundungsmodus nicht bestimmt werden kann.

Bei Erfolg **Fesetround** gibt 0 zurück. Andernfalls wird ein Wert ungleich null zurückgegeben.

## <a name="remarks"></a>Hinweise

Gleitkommaoperationen können mehrere Rundungsmodi verwenden. Diese steuern, in welche Richtung die Ergebnisse von Gleitkommaoperationen beim Speichern der Ergebnisse gerundet werden. Hiermit werden die Namen und das Verhalten der in \<<fenv.h> definierten Gleitkomma-Rundungsmakros angegeben:

|Makro|Beschreibung|
|-----------|-----------------|
|FE_DOWNWARD|Runden in Richtung minus unendlich.|
|FE_TONEAREST|Runden in Richtung des nächsten Werts.|
|FE_TOWARDZERO|Runden in Richtung 0 (null).|
|FE_UPWARD|Runden in Richtung plus unendlich.|

Das Standardverhalten von FE_TONEAREST ist, Ergebnisse in der Mitte zwischen darstellbaren Werten auf den nächsten Wert mit einem geraden (0) LSB (Least Significant Bit, niedrigstwertiges Bit) zu runden.

Der aktuelle Rundungsmodus wirkt sich auf diese Vorgänge aus:

- Zeichenfolgenkonvertierungen.

- Die Ergebnisse der arithmetischen Gleitkommaoperatoren außerhalb konstanter Ausdrücke.

- Die Bibliothek, die Funktionen, wie z. B. Rundung **Rint** und **Nearbyint**.

- Rückgabewerte aus mathematischen Funktionen der Standardbibliothek.

Der aktuelle Rundungsmodus wirkt sich auf diese Vorgänge nicht aus:

- Die **Trunc**, **ceil**, **Floor**, und **Lround** Bibliotheksfunktionen.

- Implizite Umwandlungen und Konvertierungen von Gleitkommazahl in ganze Zahl, bei denen immer in Richtung 0 (null) gerundet wird.

- Die Ergebnisse von arithmetischen Gleitkommaoperatoren in konstanten Ausdrücken, bei denen immer auf den nächsten Wert gerundet wird.

Um diese Funktionen zu verwenden, müssen Sie vor dem Aufruf Gleitkommaoptimierungen deaktivieren, die den Zugriff mithilfe der `#pragma fenv_access(on)` -Direktive verhindern könnten. Weitere Informationen finden Sie unter [fenv_access](../../preprocessor/fenv-access.md).

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**Fegetround**, **Fesetround**|\<fenv.h>|\<cfenv>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[nearbyint, nearbyintf, nearbyintl](nearbyint-nearbyintf-nearbyintl1.md)<br/>
[rint, rintf, rintl](rint-rintf-rintl.md)<br/>
[lrint, lrintf, lrintl, llrint, llrintf, llrintl](lrint-lrintf-lrintl-llrint-llrintf-llrintl.md)<br/>
