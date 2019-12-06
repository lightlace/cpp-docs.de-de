---
title: lrint, lrintf, lrintl, llrint, llrintf, llrintl
ms.date: 04/05/2018
api_name:
- lrint
- lrintl
- lrintf
- llrint
- llrintf
- llrintl
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
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
helpviewer_keywords:
- lrint function
- lrintf function
- lrintl function
- llrint function
- llrintf function
- llrintl function
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
ms.openlocfilehash: c7831842eb4d3c1eef9c4c9e83bbddb557cec0e3
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857748"
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

### <a name="parameters"></a>Parameters

*w*<br/>
Der zu rundende Wert.

## <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird der abgerundete ganzzahlige Wert von *x*zurückgegeben.

|Problem:|Zurückgeben des|
|-----------|------------|
|*x* liegt außerhalb des Bereichs des Rückgabe Typs.<br /><br /> *x* = ±<br /><br /> *x* = Nan|Löst **FE_INVALID** aus und gibt NULL (0) zurück.|

## <a name="remarks"></a>Hinweise

Da C++ das überladen zulässt, können Sie über Ladungen von **lrint** und **llrint** aufzurufen, die **float** -und **Long** **Double** -Typen annehmen. In einem C-Programm nehmen **lrint** und **llrint** immer einen **Double**-Vorgang auf.

Wenn *x* die Gleit Komma Entsprechung eines ganzzahligen Werts nicht darstellt, erhöhen diese Funktionen **FE_INEXACT**.

**Microsoft-spezifisch**: Wenn das Ergebnis außerhalb des Bereichs des Rückgabe Typs liegt oder wenn der Parameter ein NaN oder unendlich ist, wird der Rückgabewert von der Implementierung definiert. Der Microsoft-Compiler gibt den Wert 0 (null) zurück.

## <a name="requirements"></a>-Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**lrint**, **lrintf**, **lrintl**, **llrint**, **llrintf**, **llrintl**|\<math.h>|\<cmath>|

Zusätzliche Informationen zur Kompatibilität finden Sie unter [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
