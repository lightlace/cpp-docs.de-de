---
title: "frexp"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "frexp"
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
  - "frexp"
  - "_frexpl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_frexpl-Funktion"
  - "Exponent, Gleitkommazahlen"
  - "Gleitkommafunktionen, Mantissen und Exponenten"
  - "frexp-Funktion"
  - "frexpl-Funktion"
  - "Mantissen, Gleitkommavariablen"
ms.assetid: 9b020f2e-3967-45ec-a6a8-d467a071aa55
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# frexp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Mantisse und den Exponenten eine Gleitkommazahl ab.  
  
## Syntax  
  
```  
double frexp(  
   double x,  
   int *expptr   
);  
float frexp(  
   float x,  
   int * expptr  
);  // C++ only  
long double frexp(  
   long double x,  
   int * expptr  
);  // C++ only  
```  
  
#### Parameter  
 `x`  
 Gleitkommawert.  
  
 `expptr`  
 Zeiger zu gespeicherten ganzzahligem Exponenten.  
  
## Rückgabewert  
 `frexp` gibt der Mantisse zurück.  Wenn `x` 0 ist, gibt die Funktion 0 für die Mantisse und den Exponenten zurück.  Wenn `expptr``NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die Ausführung zulässig ist, um fortzufahren, Sätze `errno` dieser Funktion zu `EINVAL` und zu gibt 0 zurück.  
  
## Hinweise  
 Die `frexp`\-Funktion weist den Gleitkommawert \(`x`\) in eine Mantisse \(`m`\) und einem Exponenten \(`n`\), so, dass der absolute Wert `m` größer oder gleich 0,5 und weniger als 1,0 ist, und `x` \= `m`\*2. auf.<sup>n</sup> Der ganzzahlige Exponent `n` wird am Speicherort gespeichert, auf den durch `expptr` gezeigt wird.  
  
 C\+\+ zulässig Überladen, sodass Sie Überladungen von `frexp` aufrufen.  In einem C\-Programm verwendet `frexp` immer einen double\-Wert und eine ganze Zahl und gibt einen Double\-Wert zurück.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`frexp`|\<math.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_frexp.c  
// This program calculates frexp( 16.4, &n )  
// then displays y and n.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y;  
   int n;  
  
   x = 16.4;  
   y = frexp( x, &n );  
   printf( "frexp( %f, &n ) = %f, n = %d\n", x, y, n );  
}  
```  
  
  **frexp \(16,400000, &N\) \= 0,512500, n \= 5**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [Modf, Modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)