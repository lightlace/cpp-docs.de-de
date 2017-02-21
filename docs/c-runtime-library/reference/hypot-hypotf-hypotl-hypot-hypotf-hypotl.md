---
title: "hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_hypotf"
  - "hypot"
  - "hypotf"
  - "_hypot"
  - "_hypotl"
  - "hypotl"
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
  - "hypotf"
  - "hypotl"
  - "_hypotl"
  - "hypot"
  - "_hypot"
  - "_hypotf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_hypot-Funktion"
  - "Berechnen von Hypotenusen"
  - "hypot-Funktion"
  - "Hypotenuse berechnen"
  - "hypotf-Funktion"
  - "hypotl-Funktion"
  - "Dreiecke, Berechnen einer Hypotenuse"
ms.assetid: 6a13887f-bd53-43fc-9d77-5b42d6e49925
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# hypot, hypotf, hypotl, _hypot, _hypotf, _hypotl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet die Hypotenuse.  
  
## Syntax  
  
```  
double hypot(   
   double x,  
   double y   
);  
float hypotf(   
   float x,  
   float y   
);  
long double hypotl(  
   long double x,  
   long double y  
);  
double _hypot(   
   double x,  
   double y   
);  
float _hypotf(   
   float x,  
   float y   
);  
long double _hypotl(  
   long double x,  
   long double y  
);  
```  
  
#### Parameter  
 `x`, `y`  
 Gleitkommawerte.  
  
## Rückgabewert  
 Bei Erfolg gibt `hypot` die Länge der Hypotenuse zurück; bei Überlauf gibt `hypot` INF \(Unendlichkeit\) zurück und die `errno`\-Variable ist auf `ERANGE` festgelegt.  Sie können `_matherr` verwenden, um die Fehlerbehandlung zu ändern.  
  
 Weitere Informationen zu Rückgabecodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `hypot`\-Funktionen berechnen die Länge der Hypotenuse eines rechtwinkligen Dreiecks unter Verwendung der Länge der beiden Seiten `x` und `y` \(das heißt, die Quadratwurzel von `x`<sup>2</sup> \+ `y`<sup>2</sup>\).  
  
 Die Versionen der Funktionen mit führenden Unterstrichen unterstützen die Kompatibilität mit früheren Standards.  Ihr Verhalten ist mit den Versionen identisch, die keine führende Unterstriche haben.  Es empfiehlt sich, die Versionen ohne führende Unterstriche für neuen Code zu verwenden.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`hypot`, `hypotf`, `hypotl`, `_hypot`, `_hypotf`, `_hypotl`|\<math.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_hypot.c  
// This program prints the hypotenuse of a right triangle.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 3.0, y = 4.0;  
  
   printf( "If a right triangle has sides %2.1f and %2.1f, "  
           "its hypotenuse is %2.1f\n", x, y, _hypot( x, y ) );  
}  
```  
  
  **Wenn bei einem rechtwinkligen Dreieck die Seiten 3,0 und 4,0 sind, dann ist die Hypotenuse 5,0**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [\_cabs](../../c-runtime-library/reference/cabs.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)