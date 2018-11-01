---
title: nan, nanf, nanl
ms.date: 94/05/2018
apiname:
- nanf
- nan
- nanl
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
- nan
- nanl
- nanf
helpviewer_keywords:
- nan function
- nanf function
- nanl function
ms.assetid: 790e9158-80ab-43e0-8f5a-096198553fd9
ms.openlocfilehash: 22b0e14094a0b6f0f3571c4d7551552210177a22
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610261"
---
# <a name="nan-nanf-nanl"></a>nan, nanf, nanl

Gibt einen stillen NaN-Wert zurück.

## <a name="syntax"></a>Syntax

```C
double nan( const char* input );
float nanf( const char* input );
long double nanl( const char* input );
```

### <a name="parameters"></a>Parameter

*Eingabe*<br/>
Ein Zeichenfolgenwert.

## <a name="return-value"></a>Rückgabewert

Die **Nan** Funktionen geben einen stillen NaN-Wert zurück.

## <a name="remarks"></a>Hinweise

Die **Nan** Funktionen geben einen Gleitkommawert, der entspricht, der einem stillen (nicht signalisierenden) NaN zurück. Die *Eingabe* Wert wird ignoriert. Informationen dazu, wie ein NaN-Wert für die Ausgabe dargestellt wird, finden Sie unter [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md).

## <a name="requirements"></a>Anforderungen

|Funktion|C-Header|C++-Header|
|--------------|--------------|------------------|
|**NaN**, **Nanf**, **Nanl**|\<math.h>|\<cmath> oder \<math.h>|

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[_finite, _finitef](finite-finitef.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
