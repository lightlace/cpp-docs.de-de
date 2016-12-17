---
title: "Bessel-Funktionen: _j0, _j1, _jn, _y0, _y1, _yn"
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
  - "_j0"
  - "_j1"
  - "_jn"
  - "_y0"
  - "_y1"
  - "_yn"
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
  - "c.bessel"
  - "_j0"
  - "_j1"
  - "_jn"
  - "_y0"
  - "_y1"
  - "_yn"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Bessel-Funktionen"
  - "_j0-Funktion"
  - "_j1-Funktion"
  - "_jn-Funktion"
  - "_y0-Funktion"
  - "_y1-Funktion"
  - "_yn-Funktion"
ms.assetid: a21a8bf1-df9d-4ba0-a8c2-e7ef71921d96
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# Bessel-Funktionen: _j0, _j1, _jn, _y0, _y1, _yn
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet die Bessel\-Funktion der ersten oder zweiten Art und der 0\-ten, 1\-ten oder n\-ten Ordnung. Die Bessel\-Funktionen werden in der mathematischen Behandlung von elektromagnetischen Wellen in breitem Umfang eingesetzt.  
  
## Syntax  
  
```  
double _j0(   
   double x   
);  
double _j1(   
   double x   
);  
double _jn(   
   int n,  
   double x   
);  
double _y0(   
   double x   
);  
double _y1(   
   double x   
);  
double _yn(   
   int n,  
   double x   
);  
```  
  
#### Parameter  
 `x`  
 Gleitkommawert.  
  
 `n`  
 Ganzzahlige Ordnung der Bessel\-Funktion.  
  
## Rückgabewert  
 Jede dieser Routinen gibt eine Bessel\-Funktion von `x` zurück. Wenn `x` in der Funktion `_y0`, `_y1` oder `_yn` negativ ist, legt die Routine `errno` auf `EDOM` fest, gibt eine `_DOMAIN`\-Fehlermeldung an `stderr` aus, und gibt `_HUGE_VAL` zurück. Sie können die Fehlerbehandlung mithilfe von `_matherr` modifizieren.  
  
## Hinweise  
 Die Routinen `_j0`, `_j1` und `_jn` geben Bessel\-Funktionen der ersten Art zurück: der Ordnung 0, 1 bzw. n.  
  
|Eingabe|SEH\-Ausnahme|Matherr\-Ausnahme|  
|-------------|-------------------|-----------------------|  
|± `QNAN`,`IND`|`INVALID`|`_DOMAIN`|  
  
 Die Routinen `_y0`, `_y1` und `_yn` geben Bessel\-Funktionen der zweiten Art zurück: der Ordnung 0, 1 bzw. n.  
  
|Eingabe|SEH\-Ausnahme|Matherr\-Ausnahme|  
|-------------|-------------------|-----------------------|  
|± `QNAN`,`IND`|`INVALID`|`_DOMAIN`|  
|± 0|`ZERODIVIDE`|`_SING`|  
|&#124;x&#124;\<0,0|`INVALID`|`_DOMAIN`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_j0`, `_j1`, `_jn`, `_y0`, `_y1`, `_yn`|\<cmath\> \(C\+\+\), \<math.h\> \(C, C\+\+\)|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_bessel1.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.387;  
   int n = 3, c;  
  
   printf( "Bessel functions for x = %f:\n", x );  
   printf( " Kind   Order  Function     Result\n\n" );  
   printf( " First  0      _j0( x )     %f\n", _j0( x ) );  
   printf( " First  1      _j1( x )     %f\n", _j1( x ) );  
   for( c = 2; c < 5; c++ )  
      printf( " First  %d      _jn( %d, x )  %f\n", c, c, _jn( c, x ) );  
   printf( " Second 0      _y0( x )     %f\n", _y0( x ) );  
   printf( " Second 1      _y1( x )     %f\n", _y1( x ) );  
   for( c = 2; c < 5; c++ )  
      printf( " Second %d      _yn( %d, x )  %f\n", c, c, _yn( c, x ) );  
}  
```  
  
```Output  
Bessel-Funktionen für x = 2,387000: Art   Ordnung  Funktion     Ergebnis Erste  0      _j0( x )     0,009288 Erste  1      _j1( x )     0,522941 Erste  2      _jn( 2, x )  0,428870 Erste  3      _jn( 3, x )  0,195734 Erste  4      _jn( 4, x )  0,063131 Zweite 0      _y0( x )     0,511681 Zweite 1      _y1( x )     0,094374 Zweite 2      _yn( 2, x )  -0,432608 Zweite 3      _yn( 3, x )  -0,819314 Zweite 4      _yn( 4, x )  -1,626833  
```  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)