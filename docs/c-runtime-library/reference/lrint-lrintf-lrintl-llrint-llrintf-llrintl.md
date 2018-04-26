---
title: lrint, lrintf, lrintl, llrint, llrintf, llrintl | Microsoft-Dokumentation
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
- lrint
- lrintl
- lrintf
- llrint
- llrintf
- llrintl
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
- lrint
- lrintf
- lrintl
- llrint
- llrintf
- llrintl
- math/lrint
- math/lrintf
- math/lrintl
- math/llrint
- math/llrintf
- math/llrintl
dev_langs:
- C++
helpviewer_keywords:
- lrint function
- lrintf function
- lrintl function
- llrint function
- llrintf function
- llrintl function
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30056214b07624429c8b1b23237585e5b6f46266
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="lrint-lrintf-lrintl-llrint-llrintf-llrintl"></a>lrint, lrintf, lrintl, llrint, llrintf, llrintl

Rundet den angegebenen Gleitkommawert auf den nächsten ganzzahligen Wert mit dem aktuellen Rundungsmodus und Richtung.

## <a name="syntax"></a>Syntax

```C
long int lrint(
   double x
);

long int lrint(
   float x
); //C++ only

long int lrint(
   long double x
); //C++ only

long int lrintf(
   float x
);

long int lrintl(
   long double x
);

long long int llrint(
   double x
);

long long int llrint(
   float x
); //C++ only

long long int llrint(
   long double x
); //C++ only

long long int llrintf(
   float x
);

long long int llrintl(
   long double x
);

```

### <a name="parameters"></a>Parameter

*w*<br/>
Der zu rundende Wert.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg gibt den abgerundeten ganzzahligen Wert des *x*.

|Problem|Zurück|
|-----------|------------|
|*X* liegt außerhalb des Bereichs des Rückgabetyps<br /><br /> *X* = ±∞<br /><br /> *X* = "NaN"|Löst **FE_INVALID** und gibt 0 (null) zurück.|

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Lrint** und **Llrint** nehmen **"float"** und **lange**  **doppelte** Typen. In einem C-Programm **Lrint** und **Llrint** immer ein **doppelte**.

Wenn *x* stellt keinen dar. das Gleitkomma-Äquivalent einen ganzzahligen Wert, der diese Funktionen lösen **FE_INEXACT**.

**Microsoft-spezifisch**: Wenn das Ergebnis außerhalb des Bereichs des Rückgabetyps ist oder wenn der Parameter NaN oder unendlich ist, ist der Rückgabewert von der Implementierung abhängig. Der Microsoft-Compiler gibt den Wert 0 (null) zurück.

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**Lrint**, **Lrintf**, **Lrintl**, **Llrint**, **Llrintf**, **Llrintl**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
