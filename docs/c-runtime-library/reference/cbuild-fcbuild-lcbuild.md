---
title: _Cbuild, _FCbuild, _LCbuild | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _Cbuild function
- _FCbuild function
- _LCbuild function
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6d567dc02715b9e55644b755b6d7360f2fe3d37
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32394386"
---
# <a name="cbuild-fcbuild-lcbuild"></a>_Cbuild, _FCbuild, _LCbuild

Erstellt eine komplexe Zahl aus reellen und imaginären teilen.

## <a name="syntax"></a>Syntax

```C
_Dcomplex _Cbuild( double real, double imaginary );
_Fcomplex _FCbuild( float real, float imaginary );
_Lcomplex _LCbuild( long double real, long double imaginary );
```

### <a name="parameters"></a>Parameter

*real*<br/>
Der reelle Teil der komplexen Zahl zu erstellen.

*imaginären*<br/>
Der imaginäre Teil der komplexen Zahl zu erstellen.

## <a name="return-value"></a>Rückgabewert

Ein **_Dcomplex**, **_Fcomplex**, oder **_Lcomplex** -Struktur, die komplexe Zahl darstellt (*echte*, *imaginären*  \* ich) für Werte des angegebenen Gleitkommatyp.

## <a name="remarks"></a>Hinweise

Die **_Cbuild**, **_FCbuild**, und **_LCbuild** Funktionen vereinfachen die Erstellung komplexer Typen. Verwenden der [Creal, Crealf, Creall](creal-crealf-creall.md) und [Cimag, Cimagf, Cimagl](cimag-cimagf-cimagl.md) Funktionen zum Abrufen der reellen und imaginären Teile der komplexen Zahlen dargestellt.

## <a name="requirements"></a>Anforderungen

|Routine|C-Header|C++-Header|
|-------------|--------------|------------------|
|**_Cbuild**, **_FCbuild**, **_LCbuild**|\<complex.h>|\<ccomplex>|

Diese Funktionen sind Microsoft-spezifisch. Die Typen **_Dcomplex**, **_Fcomplex**, und **_Lcomplex** sind Microsoft-spezifische Entsprechungen zu den nicht implementierten C99 systemeigenen Typen **doppelte _Complex** , **float _Complex**, und **long double _Complex**zugeordnet. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

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
