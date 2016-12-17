---
title: "pow, powf, powl"
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
  - "powl"
  - "pow"
  - "powf"
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
  - "powl"
  - "pow"
  - "_powl"
  - "powf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_powl-Funktion"
  - "Berechnen von Exponentialen"
  - "Exponentielle Berechnungen"
  - "Potenzierung"
  - "pow-Funktion"
  - "Potenzieren, Berechnen"
  - "powf-Funktion"
  - "powl-Funktion"
ms.assetid: e75c33ed-2e59-48b1-be40-81da917324f1
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# pow, powf, powl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet `x` potenziert mit `y`.  
  
## Syntax  
  
```  
double pow(  
   double x,  
   double y   
);  
double pow(  
   double x,  
   int y  
);  // C++ only  
float pow(  
   float x,  
   float y   
);  // C++ only  
float pow(  
   float x,  
   int y  
);  // C++ only  
long double pow(  
   long double x,  
   long double y  
);  // C++ only  
long double pow(  
   long double x,  
   int y  
);  // C++ only  
float powf(  
   float x,  
   float y   
);  
long double powl(  
   long double x,  
   long double y  
);  
```  
  
#### Parameter  
 `x`  
 Basis.  
  
 `y`  
 Exponent.  
  
## Rückgabewert  
 Gibt den Wert von `x`<sup>y</sup> zurück.  Zu Überlauf oder Unterlauf wird keine Fehlermeldung ausgegeben.  
  
|Werte von x und y|Rückgabewert von "pow"|  
|-----------------------|----------------------------|  
|`x` \< \> 0 und `y` \= 0,0|1|  
|`x` \= 0,0 und `y` \= 0,0|1|  
|`x` \= 0,0 und `y` \< 0|INF|  
  
## Hinweise  
 `pow` erkennt keine ganzzahligen Gleitkommawerte, die größer als 2<sup>64</sup> sind \(z. B. `1.0E100`\).  
  
 `pow` ist eine Implementierung, die SIMD\-Streamingerweiterungen 2 \(SSE2\) verwendet.  Informationen und Einschränkungen zur Verwendung der SSE2\-Implementierung finden Sie unter [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md).  
  
 Da C\+\+ Überladungen zulässt, können Sie jede der verschiedenen Überladungen von `pow` aufrufen.  In einem C\-Programm verwendet `pow` immer zwei double\-Werte und gibt einen double\-Wert zurück.  
  
 Die `pow(int, int)`\-Überladung ist nicht mehr verfügbar.  Wenn Sie diese Überladung verwenden, kann der Compiler C2668 ausgeben.  Um dieses Problem zu vermeiden, wandeln Sie den ersten Parameter in `double`, `float` oder `long double` um.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`pow`, `powf`, `powl`|\<math.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_pow.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.0, y = 3.0, z;  
  
   z = pow( x, y );  
   printf( "%.1f to the power of %.1f is %.1f\n", x, y, z );  
}  
```  
  
## Ausgabe  
  
```  
2.0 to the power of 3.0 is 8.0  
```  
  
## .NET Framework-Entsprechung  
 [System::Math::Pow](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [sqrt, sqrtf, sqrtl](../../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)   
 [\_CIpow](../../c-runtime-library/cipow.md)