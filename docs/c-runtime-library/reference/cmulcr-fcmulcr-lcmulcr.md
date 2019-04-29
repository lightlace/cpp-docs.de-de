---
title: _Cmulcr, _FCmulcr, _LCmulcr
ms.date: 03/30/2018
apiname:
- _Cmulcr
- _FCmulcr
- _LCmulcr
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
ms.openlocfilehash: ce45b1b1081faba18d8532d3a55d1be877cf84e3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340403"
---
# <a name="cmulcr-fcmulcr-lcmulcr"></a>_Cmulcr, _FCmulcr, _LCmulcr

Multipliziert eine komplexe Zahl durch eine Gleitkommazahl.

## <a name="syntax"></a>Syntax

```C
_Dcomplex _Cmulcr( _Dcomplex x, double y );
_Fcomplex _FCmulcr( _Fcomplex x, float y );
_Lcomplex _LCmulcr( _Lcomplex x, long double y );
```

### <a name="parameters"></a>Parameter

*w*<br/>
Einer der Operanden zu multiplizierende komplexeren.

*y*<br/>
Der Gleitkomma-Operand multipliziert werden soll.

## <a name="return-value"></a>Rückgabewert

Ein **_Dcomplex**, **_Fcomplex**, oder **_Lcomplex** -Struktur, die das komplexe Produkt der komplexen Zahl darstellt *x* und Flaoting-Gleitkommazahl *y*.

## <a name="remarks"></a>Hinweise

Da die integrierten arithmetischen Operatoren nicht auf die Microsoft-Implementierung der komplexen Typen funktionieren, die **_Cmulcr**, **_FCmulcr**, und **_LCmulcr** Funktionen Vereinfachen Sie die Multiplikation von komplexen Typen von Gleitkomma-Datentypen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|C-Header|C++-Header|
|-------------|--------------|------------------|
|**_Cmulcr**, **_FCmulcr**, **_LCmulcr**|\<complex.h>|\<complex.h>|

Diese Funktionen sind Microsoft-spezifisch. Die Typen **_Dcomplex**, **_Fcomplex**, und **_Lcomplex** sind Microsoft-spezifische-Entsprechungen für den nicht implementierten C99 systemeigenen Typen **double _Complex** , **float _Complex**, und **long double _Complex**bzw. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

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
