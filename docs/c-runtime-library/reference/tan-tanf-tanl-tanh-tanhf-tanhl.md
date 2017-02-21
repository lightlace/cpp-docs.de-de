---
title: "tan, tanf, tanl, tanh, tanhf, tanhl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "tanhf"
  - "tanh"
  - "tan"
  - "tanhl"
  - "tanf"
  - "tanl"
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
  - "tanh"
  - "tan"
  - "_tanl"
  - "tanl"
  - "_tanhl"
  - "tanf"
  - "tanhf"
  - "tanhl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tanl-Funktion"
  - "tanhl-Funktion"
  - "_tanl-Funktion"
  - "_tanhl-Funktion"
  - "tan-Funktion"
  - "Berechnen von Tangenten"
  - "Tangente"
  - "tanh-Funktion"
  - "tanhf-Funktion"
  - "tanf-Funktion"
  - "Trigonometrische Funktionen"
  - "Hyperbolische Funktionen"
ms.assetid: 36cc0ce8-9c80-4653-b354-ddb3b378b6bd
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# tan, tanf, tanl, tanh, tanhf, tanhl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den Tangens \(`tan`, `tanf` oder `tanl`\) oder den Hyperbeltangens \(`tanh`, `tanhf` oder `tanhl`\).  
  
## Syntax  
  
```  
double tan(  
   double x   
);  
float tan(  
   float x   
);  // C++ only  
long double tan(  
   long double x  
);  // C++ only  
float tanf(  
   float x   
);  
long double tanl(  
   long double x  
);  
double tanh(  
   double x   
);  
float tanh(  
   float x   
);  // C++ only  
long double tanh(  
   long double x  
);  // C++ only  
float tanhf(  
   float x   
);  
long double tanhl(  
   long double x  
);  
```  
  
#### Parameter  
 `x`  
 Winkel im Bogenmaß.  
  
## Rückgabewert  
 Die `tan`\-Funktionen geben den Tangens von `x` zurück.  Wenn `x` größer oder gleich 263 oder kleiner oder gleich – 263 ist, kommt es im Ergebnis zu einem Bedeutungsverlust.  
  
 Die `tanh`\-Funktionen geben den Hyperbeltangens von `x` zurück.  Es gibt keine Fehlerrückgabe.  
  
|Eingabe|SEH\-Ausnahme|`Matherr`\-Ausnahme|  
|-------------|-------------------|-------------------------|  
|± QNAN,IND|Keine|\_DOMAIN|  
|± ∞  \(`tan`, `tanf`\)|`INVALID`|\_DOMAIN|  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `tan` und `tanh` aufrufen, die `float`\- oder `long double`\-Werte verwenden und zurückgeben.  In einem C\-Programm verwenden `tan` und `tanh` immer `double` und geben "Double" auch zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`tan`, `tanf`, `tanl`, `tanh`, `tanhf`, `tanhl`|\<math.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_tan.c  
// This program displays the tangent of pi / 4  
// and the hyperbolic tangent of the result.  
//  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double pi = 3.1415926535;  
   double x, y;  
  
   x = tan( pi / 4 );  
   y = tanh( x );  
   printf( "tan( %f ) = %f\n", pi/4, x );  
   printf( "tanh( %f ) = %f\n", x, y );  
}  
```  
  
  **tan\( 0,785398 \) \= 1,000000**  
**tanh\( 1,000000 \) \= 0,761594**   
## .NET Framework-Entsprechung  
  
-   [System::Math::Tan](https://msdn.microsoft.com/en-us/library/system.math.tan.aspx)  
  
-   [System::Math::Tanh](https://msdn.microsoft.com/en-us/library/system.math.tanh.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Long Double](../../misc/long-double.md)   
 [acos, acosf, acosl](../../c-runtime-library/reference/acos-acosf-acosl.md)   
 [asin, asinf, asinl](../../c-runtime-library/reference/asin-asinf-asinl.md)   
 [atan, atanf, atanl, atan2, atan2f, atan2l](../../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)   
 [cos, cosf, cosl, cosh, coshf, coshl](../../c-runtime-library/reference/cos-cosf-cosl-cosh-coshf-coshl.md)   
 [sin, sinf, sinl, sinh, sinhf, sinhl](../../c-runtime-library/reference/sin-sinf-sinl-sinh-sinhf-sinhl.md)   
 [\_CItan](../../c-runtime-library/citan.md)