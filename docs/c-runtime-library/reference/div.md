---
title: "div"
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
  - "div"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "div"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "div-Funktion"
  - "Dividieren von ganzen Zahlen"
  - "Quotienten"
  - "Quotienten, Berechnen"
  - "Restwerte berechnen"
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# div
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den Quotienten und den Rest von zwei ganzzahligen Werten.  
  
## Syntax  
  
```  
div_t div(   
   int numer,  
   int denom   
);  
ldiv_t div(  
   long numer,  
   long denom  
); /* C++ only */   
lldiv_t div(  
   long long numer,  
   long long denom  
); /* C++ only */  
```  
  
#### Parameter  
 `numer`  
 Der Zähler.  
  
 `denom`  
 Der Nenner.  
  
## Rückgabewert  
 `div`, welches mithilfe von Argumenten des Typs `int` aufgerufen wurde, gibt eine Struktur des Typs `div_t` zurück, die den Quotienten und den Rest enthält.  Der Rückgabewert der Überladung mit Argumenten vom Typ `long` ist `ldiv_t`.  Sowohl `div_t` als auch `ldiv_t` werden in STDLIB.H. definiert.  
  
## Hinweise  
 Die `div`\-Funktion teilt `numer` durch `denom` und berechnet dadurch den Quotienten und den Rest.  Die [div\_t](../../c-runtime-library/standard-types.md)\-Struktur enthält Quotient, `int``quot` und den Rest, `int``rem`.  Das Zeichen des Quotienten entspricht dem Zeichen des mathematischen Quotienten.  Der absolute Wert ist die größte ganze Zahl, die kleiner ist als der absolute Wert des mathematischen Quotienten.  Wenn der Nenner 0 ist, wird das Programm mit einer Fehlermeldung beendet.  
  
 Die Überladungen, die Argumente des Typs `long` oder `long long` verwenden, sind nur für C\+\+\-Code verfügbar.  Der Rückgabetyp [ldiv\_t](../../c-runtime-library/standard-types.md) enthält die Member `long``quot` und `long``rem`, und der Rückgabetyp [lldiv\_t](../../c-runtime-library/standard-types.md) enthält die Member `long long quot` und `long long rem`, die die gleiche Bedeutung wie die Member von `div_t` haben.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`div`|\<stdlib.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_div.c  
// arguments: 876 13  
  
// This example takes two integers as command-line  
// arguments and displays the results of the integer  
// division. This program accepts two arguments on the  
// command line following the program name, then calls  
// div to divide the first argument by the second.  
// Finally, it prints the structure members quot and rem.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <math.h>  
  
int main( int argc, char *argv[] )  
{  
   int x,y;  
   div_t div_result;  
  
   x = atoi( argv[1] );  
   y = atoi( argv[2] );  
  
   printf( "x is %d, y is %d\n", x, y );  
   div_result = div( x, y );  
   printf( "The quotient is %d, and the remainder is %d\n",  
           div_result.quot, div_result.rem );  
}  
```  
  
  **x ist 876, y ist 13**  
**Der Quotient ist 67 und der Rest ist 5**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)