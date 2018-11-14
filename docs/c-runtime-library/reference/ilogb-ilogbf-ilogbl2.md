---
title: Ilogb, Ilogbf, ilogbl2
ms.date: 04/05/2018
apiname:
- ilogb
- ilogbf
- ilogbl
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
- ilogb
- ilogbf
- ilogbl
- math/ilogb
- math/ilogbf
- math/ilogbl
helpviewer_keywords:
- ilogb function
- ilogbf function
- ilogbl function
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
ms.openlocfilehash: 272544124dd8a8a666fc434516d3c45c73b1d011
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519567"
---
# <a name="ilogb-ilogbf-ilogbl"></a>ilogb, ilogbf, ilogbl

Ruft eine Ganzzahl ab, die den unausgewogenen Basis-2-Exponenten des angegebenen Werts darstellt.

## <a name="syntax"></a>Syntax

```C
int ilogb(
   double x
);

int ilogb(
   float x
); //C++ only

int ilogb(
   long double x
); //C++ only

int ilogbf(
   float x
);

int ilogbl(
   long double x
);
```

### <a name="parameters"></a>Parameter

*w*<br/>
Der angegebene Wert.

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall zurückgegeben den Exponenten zur Basis 2 von *x* als signiertes **Int** Wert.

Andernfalls gibt er die folgenden, in \<math.h> definierten Werte zurück:

|Eingabe|Ergebnis|
|-----------|------------|
|±0|FP_ILOGB0|
|±INF, ±nan, unbestimmte|FP_ILOGBNAN|

Fehler werden gemäß den Angaben in [_matherr](matherr.md) gemeldet.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Ilogb** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Ilogb** immer Double und gibt eine **doppelte**.

Das Aufrufen dieser Funktion ist ähnlich wie das Aufrufen der entsprechenden **Logb** -Funktion und die anschließende Umwandlung des Rückgabewerts zu **Int**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|C-Header|C++-Header|
|-------------|--------------|------------------|
|**Ilogb**, **Ilogbf**, **Ilogbl**|\<math.h>|\<cmath>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[frexp](frexp.md)<br/>
[logb, logbf, logbl, _logb, _logbf](logb-logbf-logbl-logb-logbf.md)<br/>
