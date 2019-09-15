---
title: _scalb, _scalbf
ms.date: 04/05/2018
api_name:
- _scalb
- _scalbf
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
- scalb
- _scalb
- _scalbf
helpviewer_keywords:
- exponential calculations
- _scalb function
- _scalbf function
- scalb function
ms.assetid: 148cf5a8-b405-44bf-a1f0-7487adba2421
ms.openlocfilehash: 630a5e3db2c39cb40d31c71e6a6dfa214ed91e34
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948883"
---
# <a name="_scalb-_scalbf"></a>_scalb, _scalbf

Skaliert das Argument als zweite Potenz.

## <a name="syntax"></a>Syntax

```C
double _scalb(
   double x,
   long exp
);
float _scalbf(
   float x,
   long exp
); /* x64 only */
```

### <a name="parameters"></a>Parameter

*w*<br/>
Gleitkommawert mit doppelter Genauigkeit.

*exp*<br/>
Ganzzahlexponent.

## <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg einen Exponentialwert zurück. Bei einem Überlauf (abhängig vom Vorzeichen von *x*) gibt **_scalb** "+/- **HUGE_VAL**;" zurück. die **errno** -Variable ist auf **ERANGE**festgelegt.

Weitere Informationen zu diesem und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_scalb** -Funktion berechnet den Wert von *x* \* 2<sup>*Exp*</sup>.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_scalb**, **_scalbf**|\<float.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[ldexp](ldexp.md)<br/>
