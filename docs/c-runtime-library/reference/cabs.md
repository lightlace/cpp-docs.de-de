---
title: "_cabs"
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
  - "_cabs"
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
  - "cabsl"
  - "_cabs"
  - "_cabsl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_cabs-Funktion"
  - "_cabsl-Funktion"
  - "Absolute Werte"
  - "cabs-Funktion"
  - "cabsl-Funktion"
  - "Berechnen absoluter Werte"
ms.assetid: fea292ee-1a39-4a0a-b416-4a189346ff26
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# _cabs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den absoluten Wert einer komplexen Zahl.  
  
## Syntax  
  
```  
double _cabs(   
   struct _complex z   
);  
```  
  
#### Parameter  
 `z`  
 Komplexe Zahl.  
  
## Rückgabewert  
 `_cabs` Gibt den absoluten Wert des Arguments zurück, wenn der Vorgang erfolgreich ist.  Auf Überlauf gibt `_cabs``HUGE_VAL` zurück und legt `errno` auf `ERANGE` fest.  Sie können die Fehlerbehandlung mit [\_matherr](../../c-runtime-library/reference/matherr.md) ändern.  
  
## Hinweise  
 Die `_cabs`\-Funktion berechnet den absoluten Wert einer komplexen Zahl, die einer Struktur des Typs [\_complex](../../c-runtime-library/standard-types.md) sein muss.  Die Struktur `z` wird echter `x` \- Komponente und von imaginären `y`\- Komponente zusammen.  Ein Aufruf von `_cabs` erzeugt eine Wertentsprechung zu der Ausdrücken `sqrt`\( `z.x``*``z.x``+``z.y`\*`z.y` \).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_cabs`|\<math.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_cabs.c  
/* Using _cabs, this program calculates  
 * the absolute value of a complex number.  
 */  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   struct _complex number = { 3.0, 4.0 };  
   double d;  
  
   d = _cabs( number );  
   printf( "The absolute value of %f + %fi is %f\n",  
           number.x, number.y, d );  
}  
```  
  
  **Der absolute Wert 3,000000 \+ 4.000000I ist 5,000000**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Abs, Labs, Llabs, \_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)   
 [Fabs, Fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [labs, llabs](../../misc/labs-llabs.md)