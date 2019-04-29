---
title: _Cmulcc, _FCmulcc, _LCmulcc
ms.date: 03/30/2018
apiname:
- _Cmulcc
- _FCmulcc
- _LCmulcc
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
- _Cmulcc
- _FCmulcc
- _LCmulcc
- complex/_Cmulcc
- complex/_FCmulcc
- complex/_LCmulcc
helpviewer_keywords:
- _Cmulcc function
- _FCmulcc function
- _LCmulcc function
ms.openlocfilehash: f81ccb641a80ab264e8bc54ba1987e2c2c8469f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335379"
---
# <a name="cmulcc-fcmulcc-lcmulcc"></a>_Cmulcc, _FCmulcc, _LCmulcc

Multipliziert zwei komplexe Zahlen.

## <a name="syntax"></a>Syntax

```C
_Dcomplex _Cmulcc( _Dcomplex x, _Dcomplex y );
_Fcomplex _FCmulcc( _Fcomplex x, _Fcomplex y );
_Lcomplex _LCmulcc( _Lcomplex x, _Lcomplex y );
```

### <a name="parameters"></a>Parameter

*w*<br/>
Einer der Operanden zu multiplizierende komplexeren.

*y*<br/>
Der andere komplexe Operand multipliziert werden soll.

## <a name="return-value"></a>Rückgabewert

Ein **_Dcomplex**, **_Fcomplex**, oder **_Lcomplex** -Struktur, die das komplexe Produkt der komplexen Zahlen darstellt *x* und *y*.

## <a name="remarks"></a>Hinweise

Da die integrierten arithmetischen Operatoren nicht auf die Microsoft-Implementierung der komplexen Typen funktionieren, die **_Cmulcc**, **_FCmulcc**, und **_LCmulcc** Funktionen Vereinfachen Sie die Multiplikation von komplexen Typen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|C-Header|C++-Header|
|-------------|--------------|------------------|
|**_Cmulcc**, **_FCmulcc**, **_LCmulcc**|\<complex.h>|\<complex.h>|

Diese Funktionen sind Microsoft-spezifisch. Die Typen **_Dcomplex**, **_Fcomplex**, und **_Lcomplex** sind Microsoft-spezifische-Entsprechungen für den nicht implementierten C99 systemeigenen Typen **double _Complex** , **float _Complex**, und **long double _Complex**bzw. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[_Cmulcr, _FCmulcr, _LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
