---
title: creal, crealf, creall | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- creal
- crealf
- creall
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
- creal
- crealf
- creall
- complex/creal
- complex/crealf
- complex/creall
dev_langs:
- C++
helpviewer_keywords:
- creal function
- crealf function
- creall function
ms.assetid: fa3ac62f-7aa3-4238-a71f-d6b00cd0c7c8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a51de64d8dea595041939e8b59638031babe53a2
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="creal-crealf-creall"></a>creal, crealf, creall

Ruft den Realteil einer komplexen Zahl ab

## <a name="syntax"></a>Syntax

```C
double creal( _Dcomplex z );
float crealf( _Fcomplex z );
long double creall( _Lcomplex z );
```

```cpp
float creal( _Fcomplex z );  // C++ only
long double creal( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Parameter

*z*<br/>
Eine komplexe Zahl.

## <a name="return-value"></a>Rückgabewert

Der reelle Teil *z*.

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Creal** nehmen **_Fcomplex** oder **_Lcomplex** Werte, und der Rückgabewert **"float"** oder **long double** Werte. In einem C-Programm **Creal** immer ein **_Dcomplex** Wert und gibt eine **doppelte** Wert.

## <a name="requirements"></a>Anforderungen

|Routine|C-Header|C++-Header|
|-------------|--------------|------------------|
|**Creal**, **Crealf**, **Creall**|\<complex.h>|\<ccomplex>|

Die **_Fcomplex**, **_Dcomplex**, und **_Lcomplex** Typen sind Microsoft-spezifische-Entsprechungen der implementierten native C99 Typen **_Complex float** , **doppelte _Complex**, und **long double _Complex**zugeordnet. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[_Cbuild, _FCbuild, _LCbuild](cbuild-fcbuild-lcbuild.md)<br/>
[norm, normf, norml](norm-normf-norml1.md)<br/>
[cproj, cprojf, cprojl](cproj-cprojf-cprojl.md)<br/>
[conj, conjf, conjl](conj-conjf-conjl.md)<br/>
[cimag, cimagf, cimagl](cimag-cimagf-cimagl.md)<br/>
[carg, cargf, cargl](carg-cargf-cargl.md)<br/>
[cabs, cabsf, cabsl](cabs-cabsf-cabsl.md)<br/>