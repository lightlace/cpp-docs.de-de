---
title: "Modf, Modff, modfl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "modff"
  - "modf"
  - "modfl"
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
  - "modff"
  - "_modfl"
  - "modf"
  - "modfl"
  - "math/modf"
  - "math/modff"
  - "math/modfl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modf-Funktion"
  - "modff-Funktion"
  - "Modfl-Funktion"
ms.assetid: b1c7abf5-d476-43ca-a03c-02072a86e32d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Modf, Modff, modfl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Teilt einen Gleitkommawert in Nachkommastellen und ganze Zahlen.  
  
## Syntax  
  
```  
double modf(  
   double x,  
   double * intptr   
);  
float modf(  
   float x,  
   float * intptr  
);  // C++ only  
long double modf(  
   long double x,  
   long double * intptr  
);  // C++ only  
float modff(  
   float x,  
   float * intptr   
);  
long double modfl(  
   long double x,  
   long double * intptr  
);  
```  
  
#### Parameter  
 *w*  
 Gleitkommawert.  
  
 `intptr`  
 Zeiger auf gespeicherte Ganzzahlbereich.  
  
## Rückgabewert  
 Diese Funktion gibt den Bruchteil mit Vorzeichen des *x*. Es gibt keine Fehlerrückgabe.  
  
## Hinweise  
 Die `modf` Funktionen Zerlegen der Gleitkommawert `x` in Nachkommastellen und ganze Zahlen, von denen jedes die gleichen Vorzeichen wie hat `x`. Der Bruchteil mit Vorzeichen von `x` zurückgegeben wird. Der ganzzahlige Teil wird als Gleitkommawert an gespeichert. `intptr.`  
  
 `modf` ist eine Implementierung, die SIMD\-Streamingerweiterungen 2 \(SSE2\) verwendet. Finden Sie unter [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md) Informationen und Einschränkungen bei der Verwendung der SSE2\-Implementierung.  
  
 C\+\+ das Überladen, können Sie Überladungen von aufrufen können `modf` verwenden und zurückgeben `float` oder `long double` Parameter. In einem C\-Programm verwendet `modf` immer zwei double\-Werte und gibt einen double\-Wert zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`modf`, `modff`, `modfl`|C: \< math.h \><br /><br /> C\+\+:, \< Cmath \> oder \< math.h \>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_modf.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x, y, n;  
  
   x = -14.87654321;      /* Divide x into its fractional */  
   y = modf( x, &n );     /* and integer parts            */  
  
   printf( "For %f, the fraction is %f and the integer is %.f\n",   
           x, y, n );  
}  
```  
  
## Ausgabe  
  
```  
For -14.876543, the fraction is -0.876543 and the integer is -14  
```  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)