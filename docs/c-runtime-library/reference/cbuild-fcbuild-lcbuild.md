---
title: _Cbuild, _FCbuild, _LCbuild
ms.date: 03/30/2018
apiname:
- _Cbuild
- _FCbuild
- _LCbuild
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
- _Cbuild
- _FCbuild
- _LCbuild
- complex/_Cbuild
- complex/_FCbuild
- complex/_LCbuild
helpviewer_keywords:
- _Cbuild function
- _FCbuild function
- _LCbuild function
ms.openlocfilehash: 5565c87a3cccd1715a1357f417238587f3fba4d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340465"
---
# <a name="cbuild-fcbuild-lcbuild"></a>_Cbuild, _FCbuild, _LCbuild

Erstellt eine komplexe Zahl von reellen und imaginären Teile.

## <a name="syntax"></a>Syntax

```C
_Dcomplex _Cbuild( double real, double imaginary );
_Fcomplex _FCbuild( float real, float imaginary );
_Lcomplex _LCbuild( long double real, long double imaginary );
```

### <a name="parameters"></a>Parameter

*real*<br/>
Der reelle Teil der komplexen Zahl zu erstellen.

*imaginary*<br/>
Der imaginäre Teil der komplexen Zahl zu erstellen.

## <a name="return-value"></a>Rückgabewert

Ein **_Dcomplex**, **_Fcomplex**, oder **_Lcomplex** -Struktur, die komplexe Zahl darstellt (*echte*, *imaginären*  \* ich) für die Werte der angegebenen Gleitkomma-Typs.

## <a name="remarks"></a>Hinweise

Die **_Cbuild**, **_FCbuild**, und **_LCbuild** Funktionen vereinfachen die Erstellung von komplexen Typen. Verwenden der [Creal, Crealf, Creall](creal-crealf-creall.md) und [Cimag, Cimagf, Cimagl](cimag-cimagf-cimagl.md) Funktionen für die reellen und imaginären Teile der komplexen Zahlen dargestellt abrufen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|C-Header|C++-Header|
|-------------|--------------|------------------|
|**_Cbuild**, **_FCbuild**, **_LCbuild**|\<complex.h>|\<ccomplex>|

Diese Funktionen sind Microsoft-spezifisch. Die Typen **_Dcomplex**, **_Fcomplex**, und **_Lcomplex** sind Microsoft-spezifische-Entsprechungen für den nicht implementierten C99 systemeigenen Typen **double _Complex** , **float _Complex**, und **long double _Complex**bzw. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[_Cmulcc, _FCmulcc, _LCmulcc](cmulcc-fcmulcc-lcmulcc.md)<br/>
[_Cmulcr, _FCmulcr, _LCmulcr](cmulcr-fcmulcr-lcmulcr.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[creal, crealf, creall](creal-crealf-creall.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>
