---
title: "atanh, atanhf, atanhl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "atanhl"
  - "atanhf"
  - "atanh"
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
  - "atanhl"
  - "atanhf"
  - "atanh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atanh-Funktion"
  - "atanhf-Funktion"
  - "atanhl-Funktion"
ms.assetid: 83a43b5b-2580-4461-854f-dc84236d9f32
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# atanh, atanhf, atanhl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den umgekehrten hyperbolischen Tangens.  
  
## Syntax  
  
```  
double atanh(    double x  ); float atanh(    float x  );  // C++ only long double atanh(    long double x );  // C++ only float atanhf(    float x  ); long double atanhl(    long double x );  
```  
  
#### Parameter  
 `x`  
 Gleitkommawert.  
  
## Rückgabewert  
 Die `atanh`\-Funktionen geben den umgekehrten hyperbolischen Tangens \(hyperbolischen Arcustangens\) von `x` zurück.  Wenn `x` größer als 1 oder kleiner als –1 ist, wird `errno` auf `EDOM` gesetzt, und das Ergebnis ist ein stilles NaN.  Wenn `x` gleich 1 oder –1 ist, wird ein positiver bzw. negativer Unendlichkeitswert ausgegeben, und `errno` wird auf `ERANGE` gesetzt.  
  
|Eingabe|SEH\-Ausnahme|`Matherr`\-Ausnahme|  
|-------------|-------------------|-------------------------|  
|± QNAN,IND|Keine|Keine|  
|`X` ≥ 1; `x` ≤ \-1|Keine|Keine|  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `atanh` aufrufen, die `float` oder `long double`\-Werte verwenden und zurückgeben.  In einem C\-Programm verwendet `atanh` immer `double` und gibt diesen Wert zurück.  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`atanh`, `atanhf`, `atanhl`|\<math.h\>|\<cmath\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_atanh.c  
// This program displays the hyperbolic tangent of pi / 4  
// and the arc hyperbolic tangent of the result.  
//  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = tanh( pi / 4 );  
   y = atanh( x );  
   printf( "tanh( %f ) = %f\n", pi/4, x );  
   printf( "atanh( %f ) = %f\n", x, y );  
}  
```  
  
  **tanh\( 0,785398 \) \= 0,655794**  
**atanh \(0,655794\) \= 0,785398**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Long Double](../../misc/long-double.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [tan, tanf, tanl, tanh, tanhf, tanhl](../../c-runtime-library/reference/tan-tanf-tanl-tanh-tanhf-tanhl.md)   
 [\_CItan](../../c-runtime-library/citan.md)