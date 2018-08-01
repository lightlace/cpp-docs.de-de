---
title: acos, acosf, acosl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- acosf
- acos
- acosl
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
- acos
- acosl
- acosf
- math/acosf
- math/acosl
dev_langs:
- C++
helpviewer_keywords:
- acos function
- acosl function
- acosf function
- trigonometric functions
- arccosine function
ms.assetid: 00b89c48-8faf-4824-aa95-fa4349a4975d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5384d4e97ebb4f3f6152278e916c02bb350090ea
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401937"
---
# <a name="acos-acosf-acosl"></a>acos, acosf, acosl

Berechnet den Arkuskosinus.

## <a name="syntax"></a>Syntax

```C
double acos( double x );
float acosf( float x );
long double acosl( long double x );
```

```cpp
float acos( float x );   // C++ only
long double acos( long double x );   // C++ only
```

### <a name="parameters"></a>Parameter

*w*  
Der Wert zwischen-1 und 1, für die den Arkuskosinus (dem Arkuskosinus) berechnet werden soll.

## <a name="return-value"></a>Rückgabewert

Die **Acos** Funktion gibt den Arkuskosinus *x* im Bereich von 0 bis π rad.

In der Standardeinstellung Wenn *x* ist kleiner als-1 oder größer als 1 ist, **Acos** einen unbestimmten Wert zurück.

|Eingabe|SEH-Ausnahme|Matherr-Ausnahme|
|-----------|-------------------|-----------------------|
|± ∞|INVALID|_DOMAIN|
|± QNAN,IND|Keine|_DOMAIN|
|&#124;x&#124;>1|INVALID|_DOMAIN|

## <a name="remarks"></a>Hinweise

Da C++ das Überladen zulässt, können Sie Überladungen von Aufrufen **Acos** verwenden und zurückgeben **"float"** und **lange** **doppelte** Typen. In einem C-Programm **Acos** immer Double und gibt eine **doppelte**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionale Header|
|-------------|---------------------|----------------------|
|**ACOS**, **Acosf**, **Acosl**|\<math.h>|\<errno.h>|

## <a name="example"></a>Beispiel

Dieses Programm fordert zur Eingabe eines Werts im – 1 bis 1 auf. Eingabewerte außerhalb dieses Bereichs erzeugen `_DOMAIN`-Fehlermeldungen. Wenn ein gültiger Wert eingegeben wird, gibt das Programm den Arkussinus und den Arkuskosinus dieses Werts aus.

```C
// crt_asincos.c
// arguments: 0

#include <math.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( int ac, char* av[] )
{
    double  x,
            y;
    errno_t err;

    // argument checking
    if (ac != 2)
    {
        fprintf_s( stderr, "Usage: %s <number between -1 and 1>\n",
                   av[0]);
        return 1;
    }

    // Convert argument into a double value
    if ((err = sscanf_s( av[1], "%lf", &x )) != 1)
    {
        fprintf_s( stderr, "Error converting argument into ",
                   "double value.\n");
        return 1;
    }

    // Arcsine of X
    y = asin( x );
    printf_s( "Arcsine of %f = %f\n", x, y );

    // Arccosine of X
    y = acos( x );
    printf_s( "Arccosine of %f = %f\n", x, y );
}
```

```Output
Arcsine of 0.000000 = 0.000000
Arccosine of 0.000000 = 1.570796
```

## <a name="see-also"></a>Siehe auch

[Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)  
[asin, asinf, asinl](asin-asinf-asinl.md)  
[atan, atanf, atanl, atan2, atan2f, atan2l](atan-atanf-atanl-atan2-atan2f-atan2l.md)  
[cos, cosf, cosl](cos-cosf-cosl.md)  
[_matherr](matherr.md)  
[sin, sinf, sinl](sin-sinf-sinl.md)  
[tan, tanf, tanl](tan-tanf-tanl.md)  