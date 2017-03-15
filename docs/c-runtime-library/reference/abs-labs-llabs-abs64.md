---
title: "Abs, Labs, Llabs, _abs64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "abs"
  - "_abs64"
  - "labs"
  - "llabs"
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
  - "stdlib/_abs64"
  - "math/abs"
  - "_abs64"
  - "abs"
  - "labs"
  - "math/labs"
  - "llabs"
  - "math/llabs"
  - "cmath/abs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Absolute Werte"
  - "abs-Funktion"
  - "abs64-Funktion"
  - "_abs64-Funktion"
  - "Berechnen absoluter Werte"
ms.assetid: 60f789d1-4a1e-49f5-9e4e-0bdb277ea26a
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# Abs, Labs, Llabs, _abs64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet den absoluten Wert des Arguments.  
  
## Syntax  
  
```  
int abs(   
   int n   
);  
long abs(   
   long n   
);   // C++ only  
long long abs(   
   long long n   
);   // C++ only  
double abs(   
   double n   
);   // C++ only  
long double abs(  
   long double n  
);   // C++ only  
float abs(  
   float n   
);   // C++ only  
long labs(  
   long n   
);  
long long llabs(  
   long long n   
);  
__int64 _abs64(   
   __int64 n   
);  
```  
  
#### Parameter  
 `n`  
 Der numerische Wert.  
  
## Rückgabewert  
 Die `abs`, `labs`, `llabs` und `_abs64` Funktionen zurück, den absoluten Wert des Parameters `n`. Es gibt keine Fehlerrückgabe.  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `abs`aufrufen, die `long`\-, `long long`\-, `float`\-, `double`\- und `long double`\-Werte verwenden und zurückgeben. Diese Überladungen sind in den Header \< Cmath \> definiert. In einem C\-Programm verwendet `abs` immer "int" und gibt auch "int" zurück.  
  
 **Microsoft\-spezifisch**  
  
 Da der Bereich von negativen ganzen Zahlen, die mithilfe eines Ganzzahltyps darstellbare größer als der Bereich von positiven ganzen Zahlen, die ist mithilfe dieses Typs dargestellt werden können, ist es möglich, ein Argument für diese Funktionen bereitstellen, die nicht konvertiert werden kann. Wenn der absolute Wert des Arguments nicht über den Rückgabetyp dargestellt werden kann, geben die `abs`\-Funktionen den Argumentwert unverändert zurück. Insbesondere gibt `abs(INT_MIN)``INT_MIN` zurück, `labs(LONG_MIN)` gibt `LONG_MIN` zurück, `llabs(LLONG_MIN)` gibt `LLONG_MIN` zurück und `_abs64(_I64_MIN)` gibt `_I64_MIN` zurück. Dies bedeutet, dass die `abs`\-Funktionen nicht verwendet werden können, um einen positiven Wert sicherzustellen.  
  
 **Ende Microsoft\-spezifisch**  
  
## Anforderungen  
  
|Routine|Erforderliche C\-Headerdatei|Erforderlicher C\+\+\-header|  
|-------------|----------------------------------|----------------------------------|  
|`abs`, `labs`, `llabs`|\< math.h \> oder \< stdlib.h \>|\< Cmath \>, \< Cstdlib \>, \< stdlib.h \> oder \< math.h \>|  
|`_abs64`|\<stdlib.h\>|\< Cstdlib \> oder \< stdlib.h \>|  
  
 Verwenden Sie die überladenen Versionen der `abs` in C\+\+ müssen Sie den Header \< Cmath \> enthalten.  
  
## Beispiel  
 Dieses Programm berechnet die absoluten Werte einiger Zahlen und zeigt sie an.  
  
```c  
// crt_abs.c  
// Build: cl /W3 /TC crt_abs.c  
// This program demonstrates the use of the abs function  
// by computing and displaying the absolute values of  
// several numbers.  
  
#include <stdio.h>  
#include <math.h>  
#include <stdlib.h>  
#include <limits.h>  
  
int main( void )  
{  
    int ix = -4;  
    long lx = -41567L;  
    long long llx = -9876543210LL;  
    __int64 wx = -1;  
  
    // absolute 32 bit integer value  
    printf_s("The absolute value of %d is %d\n", ix, abs(ix));  
  
    // absolute long integer value  
    printf_s("The absolute value of %ld is %ld\n", lx, labs(lx));  
  
    // absolute long long integer value  
    printf_s("The absolute value of %lld is %lld\n", llx, llabs(llx));  
  
    // absolute 64 bit integer value  
    printf_s("The absolute value of 0x%.16I64x is 0x%.16I64x\n", wx,   
        _abs64(wx));  
  
    // Integer error cases:  
    printf_s("Microsoft implementation-specific results:\n");  
    printf_s(" abs(INT_MIN) returns %d\n", abs(INT_MIN));  
    printf_s(" labs(LONG_MIN) returns %ld\n", labs(LONG_MIN));  
    printf_s(" llabs(LLONG_MIN) returns %lld\n", llabs(LLONG_MIN));  
    printf_s(" _abs64(_I64_MIN) returns 0x%.16I64x\n", _abs64(_I64_MIN));  
}  
```  
  
```Output  
Der Absolute Wert von-4 ist 4, die den absoluten Wert von – 41567 ist 41567 der Absolute Wert von – 9876543210 ist 9876543210 der Absolute Wert von 0xffffffffffffffff ist 0 x 0000000000000001 Microsoft-Implementierung abhängige Ergebnisse: abs(INT_MIN) gibt – 2147483648 labs(LONG_MIN) gibt – 2147483648 llabs gibt-9223372036854775808 _abs64(_I64_MIN) gibt 0 x 8000000000000000 zurück  
  
```  
  
## .NET Framework-Entsprechung  
 [System::Math::Abs](https://msdn.microsoft.com/en-us/library/system.math.abs.aspx)  
  
## Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [\_cabs](../../c-runtime-library/reference/cabs.md)   
 [Fabs, Fabsf, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [imaxabs](../../c-runtime-library/reference/imaxabs.md)