---
title: clog10, clog10f, clog10l
ms.date: 11/04/2016
api_name:
- clog10
- clog10f
- clog10l
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
- clog10
- clog10f
- clog10l
- complex/clog10
- complex/clog10f
- complex/clog10l
helpviewer_keywords:
- clog10 function
- clog10f function
- clog10l function
ms.assetid: 2ddae00d-ef93-4441-add3-f4d58358401b
ms.openlocfilehash: a840494caf3c34f09d8c90970988e847be712cb4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939112"
---
# <a name="clog10-clog10f-clog10l"></a>clog10, clog10f, clog10l

Ruft den Logarithmus zur Basis 10 einer komplexen Zahl ab.

## <a name="syntax"></a>Syntax

```C
_Dcomplex clog10( _Dcomplex z );
_Fcomplex clog10f( _Fcomplex z );
_Lcomplex clog10l( _Lcomplex z );
```

```cpp
_Fcomplex clog10( _Fcomplex z );  // C++ only
_Lcomplex clog10( _Lcomplex z );  // C++ only
```

### <a name="parameters"></a>Parameter

*z*<br/>
Die Basis des Logarithmus.

## <a name="return-value"></a>Rückgabewert

Die möglichen Rückgabewerte sind:

|z Parameter|Rückgabewert|
|-----------------|------------------|
|Positiv|Der Logarithmus zur Basis 10 von z|
|Zero|- ∞|
|Negativ|NaN|
|NaN|NaN|
|+ ∞|+ ∞|

## <a name="remarks"></a>Hinweise

Da C++ das überladen zulässt, können Sie über Ladungen von **clog10** aufzurufen, die **_Fcomplex** -und **_Lcomplex** -Werte verwenden und zurückgeben. In einem C-Programm nimmt **clog10** immer einen **_Dcomplex** -Wert an und gibt diesen zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|C-Header|C++-Header|
|-------------|--------------|------------------|
|**clog10**, **clog10f**, **clogl**|\<complex.h>|\<ccomplex>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Alphabetische Funktionsreferenz](crt-alphabetical-function-reference.md)<br/>
[cexp, cexpf, cexpl](cexp-cexpf-cexpl.md)<br/>
[cpow, cpowf, cpowl](cpow-cpowf-cpowl.md)<br/>
[clog, clogf, clogl](clog-clogf-clogl.md)<br/>
