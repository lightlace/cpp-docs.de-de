---
title: "acos, acosf, acosl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "acosf"
  - "acos"
  - "acosl"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "acos"
  - "acosl"
  - "acosf"
  - "math/acosf"
  - "math/acosl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "acos-Funktion"
  - "acosf-Funktion"
  - "acosl-Funktion"
  - "arccosine-Funktion"
  - "Trigonometrische Funktionen"
ms.assetid: 00b89c48-8faf-4824-aa95-fa4349a4975d
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# acos, acosf, acosl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den Arkuskosinus.  
  
## Syntax  
  
```  
double acos(   
   double x   
);  
float acos(  
   float x   
);   // C++ only  
long double acos(  
   long double x  
);   // C++ only  
float acosf(  
   float x   
);  
long double acosl(  
   long double x  
);  
```  
  
#### Parameter  
 `x`  
 Wert zwischen – 1 und 1, für den der Arkuskosinus berechnet werden soll \(der umgekehrte Kosinus\).  
  
## Rückgabewert  
 Die `acos`\-Funktion gibt den Arkuskosinus von `x` im Bogenmaß im Bereich 0 bis π zurück.  
  
 Wenn `x` kleiner als – 1 oder größer als 1 ist, gibt `acos` standardmäßig einen unbestimmten Wert zurück.  
  
|Eingabe|SEH\-Ausnahme|Matherr\-Ausnahme|  
|-------------|-------------------|-----------------------|  
|± ∞|`INVALID`|`_DOMAIN`|  
|± QNAN,IND|Keine|`_DOMAIN`|  
|&#124;x&#124;\>1|`INVALID`|`_DOMAIN`|  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `acos` aufrufen, die `float` und `long double`\-Typen verwenden und zurückgeben.  In einem C\-Programm verwendet `acos` immer `double` und gibt diesen Wert zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionale Header|  
|-------------|---------------------------|----------------------|  
|`acos`, `acosf`, `acosl`|\<math.h\>|\<errno.h\>|  
  
## Beispiel  
 Dieses Programm fordert zur Eingabe eines Werts im – 1 bis 1 auf.  Eingabewerte außerhalb dieses Bereichs erzeugen `_DOMAIN`\-Fehlermeldungen.  Wenn ein gültiger Wert eingegeben wird, gibt das Programm den Arkussinus und den Arkuskosinus dieses Werts aus.  
  
```  
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
  
  **Arkussinus von 0,000000 \= 0,000000**  
**Arkuskosinus von 0,000000 \= 1,570796**   
## .NET Framework-Entsprechung  
 [System::Math::Acos](https://msdn.microsoft.com/en-us/library/system.math.acos.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)