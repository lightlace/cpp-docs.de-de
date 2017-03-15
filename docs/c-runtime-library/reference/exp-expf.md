---
title: "exp, expf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "expf"
  - "exp"
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
  - "_expl"
  - "expf"
  - "exp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exponentielle Berechnungen"
  - "expf-Funktion"
  - "Berechnen von Exponentialen"
  - "exp-Funktion"
ms.assetid: 7070016d-1143-407e-9e9a-6b059bb88867
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# exp, expf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet die Exponentialfunktion.  
  
## Syntax  
  
```  
double exp(   
   double x  
);  
float exp(  
   float x  
);  // C++ only  
long double exp(  
   long double x  
);  // C++ only  
float expf(   
   float x  
);  
```  
  
#### Parameter  
 `x`  
 Gleitkommawert.  
  
## Rückgabewert  
 Die `exp`\-Funktion gibt den Wert des Gleitkommaparameters exponentiellen, `x` zurück, wenn der Vorgang erfolgreich ist.  Das heißt, ist das Ergebnis e Potenz `x`, in der e die Basis des natürlichen Logarithmus ist.  Auf Überlauf gibt die Funktion INF \(unendlich\) und auf Unterlauf, `exp` gibt 0 zurück.  
  
|Eingabe|SEH\-Ausnahme|Matherr\-Ausnahme|  
|-------------|-------------------|-----------------------|  
|± QNAN,IND|Kein|\_DOMAIN|  
|± ∞|INVALID|\_DOMAIN|  
|x ≥ 7.097827e\+002|INEXACT\+OVERFLOW|OVERFLOW|  
|X ≤ \-7.083964e\+002|INEXACT\+UNDERFLOW|UNTERLAUF|  
  
 `exp` ist eine Implementierung, die SIMD\-Streamingerweiterungen 2 \(SSE2\) verwendet.  Weitere Informationen finden Sie unter [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md) und Anwendungseinschränkungen die Implementierung SSE2\-Anweisungen.  
  
## Hinweise  
 C\+\+ zulässig Überladen, sodass Sie Überladungen von `exp` aufrufen.  In einem C\-Programm verwendet `exp` immer double und gibt auch double zurück.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`exp`, `expf`|\<math.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_exp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.302585093, y;  
  
   y = exp( x );  
   printf( "exp( %f ) = %f\n", x, y );  
}  
```  
  
  **exp \(2,302585\) \= 10,000000**   
## .NET Framework-Entsprechung  
 [System::Math::Exp](https://msdn.microsoft.com/en-us/library/system.math.exp.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [\_CIexp](../../c-runtime-library/ciexp.md)