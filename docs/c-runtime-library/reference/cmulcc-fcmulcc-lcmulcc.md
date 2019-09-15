---
title: _Cmulcc, _FCmulcc, _LCmulcc
ms.date: 03/30/2018
api_name:
- _Cmulcc
- _FCmulcc
- _LCmulcc
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
ms.openlocfilehash: fc21f8cbd2103993bc2b3e36020c57c8520f04a1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939077"
---
# <a name="_cmulcc-_fcmulcc-_lcmulcc"></a>_Cmulcc, _FCmulcc, _LCmulcc

Multipliziert zwei komplexe Zahlen.

## <a name="syntax"></a>Syntax

```C
_Dcomplex _Cmulcc( _Dcomplex x, _Dcomplex y );
_Fcomplex _FCmulcc( _Fcomplex x, _Fcomplex y );
_Lcomplex _LCmulcc( _Lcomplex x, _Lcomplex y );
```

### <a name="parameters"></a>Parameter

*w*<br/>
Einer der komplexen Operanden, die multipliziert werden sollen.

*y*<br/>
Der andere komplexe Operand, der multipliziert werden soll.

## <a name="return-value"></a>Rückgabewert

Eine **_Dcomplex**-, **_Fcomplex**-oder **_Lcomplex** -Struktur, die das komplexe Produkt der komplexen Zahlen *x* und *y*darstellt.

## <a name="remarks"></a>Hinweise

Da die integrierten arithmetischen Operatoren in der Microsoft-Implementierung der komplexen Typen nicht funktionieren, vereinfachen die Funktionen **_Cmulcc**, **_FCmulcc**und **_LCmulcc** die Multiplikation komplexer Typen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|C-Header|C++-Header|
|-------------|--------------|------------------|
|**_Cmulcc**, **_FCmulcc**, **_LCmulcc**|\<complex.h>|\<complex.h>|

Diese Funktionen sind Microsoft-spezifisch. Die Typen **_Dcomplex**, **_Fcomplex**und **_Lcomplex** sind Microsoft-spezifische Entsprechungen für die nicht implementierten C99 Native C99-Typen **Double _Complex**, **float _Complex**und **long Double _Complex**. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

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
