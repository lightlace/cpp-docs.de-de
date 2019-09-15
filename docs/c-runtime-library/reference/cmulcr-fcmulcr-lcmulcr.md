---
title: _Cmulcr, _FCmulcr, _LCmulcr
ms.date: 03/30/2018
api_name:
- _Cmulcr
- _FCmulcr
- _LCmulcr
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
- _Cmulcr
- _FCmulcr
- _LCmulcr
- complex/_Cmulcr
- complex/_FCmulcr
- complex/_LCmulcr
helpviewer_keywords:
- _Cmulcr function
- _FCmulcr function
- _LCmulcr function
ms.openlocfilehash: cbff1c2cb0e66da77b6fdc8127b78fb475aa5080
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942891"
---
# <a name="_cmulcr-_fcmulcr-_lcmulcr"></a>_Cmulcr, _FCmulcr, _LCmulcr

Multipliziert eine komplexe Zahl mit einer Gleit Komma Zahl.

## <a name="syntax"></a>Syntax

```C
_Dcomplex _Cmulcr( _Dcomplex x, double y );
_Fcomplex _FCmulcr( _Fcomplex x, float y );
_Lcomplex _LCmulcr( _Lcomplex x, long double y );
```

### <a name="parameters"></a>Parameter

*w*<br/>
Einer der komplexen Operanden, die multipliziert werden sollen.

*y*<br/>
Der zu multiplizierende Gleit Komma Operand.

## <a name="return-value"></a>Rückgabewert

Eine **_Dcomplex**-, **_Fcomplex**-oder **_Lcomplex** -Struktur, die das komplexe Produkt der komplexen Zahl *x* und der flaoting-Punkt Zahl *y*darstellt.

## <a name="remarks"></a>Hinweise

Da die integrierten arithmetischen Operatoren in der Microsoft-Implementierung der komplexen Typen nicht funktionieren, vereinfachen die Funktionen **_Cmulcr**, **_FCmulcr**und **_LCmulcr** die Multiplikation komplexer Typen durch Gleit Komma Typen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|C-Header|C++-Header|
|-------------|--------------|------------------|
|**_Cmulcr**, **_FCmulcr**, **_LCmulcr**|\<complex.h>|\<complex.h>|

Diese Funktionen sind Microsoft-spezifisch. Die Typen **_Dcomplex**, **_Fcomplex**und **_Lcomplex** sind Microsoft-spezifische Entsprechungen für die nicht implementierten C99 Native C99-Typen **Double _Complex**, **float _Complex**und **long Double _Complex**. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcc, _FCmulcc, _LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
