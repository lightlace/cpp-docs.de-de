---
title: "fmod, fmodf"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "fmod"
  - "fmodf"
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
  - "fmod"
  - "_fmodl"
  - "fmodf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Berechnen von Gleitkommarestwerten"
  - "fmodf-Funktion"
  - "fmod-Funktion"
  - "Gleitkommazahlen, Berechnen von Restwerten"
ms.assetid: 6962d369-d11f-40b1-a6d7-6f67239f8a23
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# fmod, fmodf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den Gleitkommarest.  
  
## Syntax  
  
```  
double fmod(   
   double x,  
   double y   
);  
float fmod(  
   float x,  
   float y   
);  // C++ only  
long double fmod(  
   long double x,  
   long double y  
);  // C++ only  
float fmodf(   
   float x,  
   float y   
);  
```  
  
#### Parameter  
 `x`, `y`  
 Gleitkommawerte.  
  
## Rückgabewert  
 `fmod` gibt den Gleitkommarest von `x` \/ `y` zurück.  Wenn der Wert von `y` 0,0 ist, gibt `fmod` ein stilles NaN zurück.  Informationen zur Darstellung eines stillen nan durch die `printf` \- Familie, finden Sie unter [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## Hinweise  
 Die `fmod`\-Funktion berechnet den Gleitkommarest `f` von `x` \/ `y` wie etwa `x` \= `i` `*` `y` \+ `f`, wobei `i` eine ganze Zahl ist, `f` das gleiche Zeichen wie `x` hat und der absolute Wert von `f` kleiner ist als der absolute Wert von `y`.  
  
 C\+\+ zulässig Überladen, sodass Sie Überladungen von `fmod` aufrufen.  In einem C\-Programm verwendet `fmod` immer zwei Double und gibt einen Double zurück.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fmod`, `fmodf`|\<math.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_fmod.c  
// This program displays a floating-point remainder.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double w = -10.0, x = 3.0, z;  
  
   z = fmod( w, x );  
   printf( "The remainder of %.2f / %.2f is %f\n", w, x, z );  
}  
```  
  
  **Der Rest von – 10.00 \/ 3.00 ist – 1,000000**   
## .NET Framework-Entsprechung  
 [System::Math::IEEERemainder](https://msdn.microsoft.com/en-us/library/system.math.ieeeremainder.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [Fabs, Fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [\_CIfmod](../../c-runtime-library/cifmod.md)