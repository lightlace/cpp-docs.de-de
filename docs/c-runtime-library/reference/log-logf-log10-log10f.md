---
title: "log, logf, log10, log10f"
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
  - "log10f"
  - "logf"
  - "log10"
  - "log"
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
  - "logf"
  - "_log10l"
  - "log"
  - "_logl"
  - "log10f"
  - "log10"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Berechnen von Logarithmen"
  - "log10f-Funktion"
  - "log10-Funktion"
  - "log-Funktion"
  - "logf-Funktion"
  - "Logarithmen"
ms.assetid: 7adc77c2-04f7-4245-a980-21215563cfae
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# log, logf, log10, log10f
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet Logarithmus.  
  
## Syntax  
  
```  
  
      double log(  
   double x   
);  
float log(  
   float x  
);  // C++ only  
long double log(  
   long double x  
);  // C++ only  
float logf(  
   float x   
);  
double log10(  
   double x  
);  
float log10(  
   float x  
);  // C++ only  
long double log10(  
   long double x  
);  // C++ only  
float log10f (  
   float x  
);  
```  
  
#### Parameter  
 *x*  
 Wert, dessen Logarithmus durchsucht werden soll.  
  
## Rückgabewert  
 Die **log**\-Funktionen geben den natürlichen Logarithmus zurück \(Basis e\) von *x,* wenn erfolgreich.  Die Funktionen log10 geben den Logarithmus zur Basis 10 zurück.  Wenn *x* negativ ist, geben diese Funktionen ein unterbreitet, standardmäßig zurück.  Wenn *x* 0 ist, geben sie INF zurück \(unendlich\).  
  
|Eingabe|SEH\-Ausnahme|Matherr\-Ausnahme|  
|-------------|-------------------|-----------------------|  
|± QNAN,IND|Keine|\_DOMAIN|  
|± 0|ZERODIVIDE|\_SING|  
|x \< 0|INVALID|\_DOMAIN|  
  
 **log** und `log10` verfügt eine Implementierung, die zusätzlich SIMD Extensions SSE2\-Anweisungen \(2\) verwendet.  Weitere Informationen finden Sie unter [\_set\_SSE2\_enable](../../c-runtime-library/reference/set-sse2-enable.md) und Anwendungseinschränkungen die Implementierung SSE2\-Anweisungen.  
  
## Hinweise  
 C\+\+ zulässig Überladen, sodass Sie Überladungen von **log** und `log10` aufrufen.  In einem C\-Programm nehmen **log** und `log10` geben immer und double zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|**log**, `logf`, `log10`, `log10f`|\<math.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_log.c  
/* This program uses log and log10  
 * to calculate the natural logarithm and  
 * the base-10 logarithm of 9,000.  
 */  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 9000.0;  
   double y;  
  
   y = log( x );  
   printf( "log( %.2f ) = %f\n", x, y );  
   y = log10( x );  
   printf( "log10( %.2f ) = %f\n", x, y );  
}  
```  
  
## Ausgabe  
  
```  
log( 9000.00 ) = 9.104980  
log10( 9000.00 ) = 3.954243  
```  
  
 Um Logarithmus für andere Basiszahlen zu generieren, verwenden Sie die mathematische Beziehung: protokollieren Sie zur Basis b eines \=\= natürlichen Logarithmus \(a\)\/des natürlichen Logarithmus \(b\).  
  
```  
// logbase.cpp  
#include <math.h>  
#include <stdio.h>  
  
double logbase(double a, double base)  
{  
   return log(a) / log(base);  
}  
  
int main()  
{  
   double x = 65536;  
   double result;  
  
   result = logbase(x, 2);  
   printf("Log base 2 of %lf is %lf\n", x, result);  
}  
```  
  
## Ausgabe  
  
```  
Log base 2 of 65536.000000 is 16.000000  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::Math::Log](https://msdn.microsoft.com/en-us/library/system.math.log.aspx)  
  
-   [System::Math::Log10](https://msdn.microsoft.com/en-us/library/system.math.log10.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [\_matherr](../../c-runtime-library/reference/matherr.md)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)   
 [\_CIlog](../../c-runtime-library/cilog.md)   
 [\_CIlog10](../../c-runtime-library/cilog10.md)