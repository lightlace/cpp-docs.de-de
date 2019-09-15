---
title: asin, asinf, asinl
ms.date: 04/05/2018
api_name:
- asinf
- asinl
- asin
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
- asin
- asinl
- asinf
helpviewer_keywords:
- asin function
- asinl function
- asinf function
- trigonometric functions
- arcsine function
ms.assetid: ca05f9ea-b711-49f6-9f32-2f4019abfd69
ms.openlocfilehash: 1e70c9b2187b97d3dea589c1757081da8bf2bd10
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943650"
---
# <a name="asin-asinf-asinl"></a>asin, asinf, asinl

Berechnet den Arkussinus.

## <a name="syntax"></a>Syntax

```C
double asin( double x );
float asinf ( float x );
long double asinl( long double x );
```

```cpp
float asin( float x );  // C++ only
long double asin( long double x );  // C++ only
```

### <a name="parameters"></a>Parameter

*w*<br/>
Wert, dessen Arkussinus berechnet werden soll.

## <a name="return-value"></a>Rückgabewert

Die **ASIN** -Funktion gibt den Arkus Sinus (die umgekehrte Sinusfunktion) von x im Bereich von "Bereich-/2" bis " *x* 2" zurück.

Wenn *x* kleiner als-1 oder größer als 1 ist, gibt **ASIN** standardmäßig einen unbestimmten Wert zurück.

|Eingabe|SEH-Ausnahme|Matherr-Ausnahme|
|-----------|-------------------|-----------------------|
|± ∞|**UNGÜLTIG**|**_DOMAIN**|
|± **QNAN**, **IND**|none|**_DOMAIN**|
|&#124;x&#124;>1|**UNGÜLTIG**|**_DOMAIN**|

## <a name="remarks"></a>Hinweise

Da C++ das überladen zulässt, können Sie über Ladungen von **ASIN** mit **float** -und **Long** **Double** -Werten aufzurufen. In einem C-Programm nimmt **ASIN** immer einen **Double**-Wert an und gibt ihn zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header (C)|Erforderlicher Header (C++)|
|-------------|---------------------|-|
|**asin**, **asinf**, **asinl**|\<math.h>|\<cmath> oder \<math.h>|

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie unter [acos, acosf, acosl](acos-acosf-acosl.md).

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)<br/>
[acos, acosf, acosl](acos-acosf-acosl.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[_matherr](matherr.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
[tan, tanf, tanl](tan-tanf-tanl.md)<br/>
