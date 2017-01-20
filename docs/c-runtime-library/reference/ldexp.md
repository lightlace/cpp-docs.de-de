---
title: "ldexp"
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
  - "ldexp"
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
  - "ldexp"
  - "_ldexpl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Berechnen reeller Zahlen"
  - "Berechnen reeller Zahlen"
  - "Exponent, Gleitkommazahlen"
  - "Gleitkommafunktionen, Mantissen und Exponenten"
  - "ldexp-Funktion"
  - "Mantissen, Gleitkommavariablen"
ms.assetid: aa7f5310-3879-4f63-ae74-86a39fbdedfa
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# ldexp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Multipliziert eine Gleitkommazahl mit einer ganzzahligen Potenz von zwei.  
  
## Syntax  
  
```  
double ldexp(    double x,    int exp  ); float ldexp(    float x,    int exp );  // C++ only long double ldexp(    long double x,    int exp );  // C++ only  float ldexpf(    float x,    int exp );  long double ldexpl(    long double x,    int exp );   
```  
  
#### Parameter  
 `x`  
 Gleitkommawert.  
  
 `exp`  
 Ganzzahlexponent.  
  
## Rückgabewert  
 Bei Erfolg gibt die `ldexp`\-Funktion gibt den Wert `x` \* 2<sup>exp</sup> zurück.  Bei einem Überlauf und abhängig vom Vorzeichen von `x` gibt `ldexp` \+\/– `HUGE_VAL` zurück. Der `errno`\-Wert wird auf `ERANGE` gesetzt.  
  
 Weitere Informationen über `errno` und mögliche Fehlerrückgabewerte finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `ldexp` aufrufen, die `float` oder `long double`\-Typen verwenden.  In einem C\-Programm verwendet `ldexp` immer `double` und `int` und gibt `double` zurück.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`ldexp`, `ldexpf`, `ldexpl`|\<math.h\>|\<cmath\>|  
  
 Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_ldexp.c  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 4.0, y;  
   int p = 3;  
  
   y = ldexp( x, p );  
   printf( "%2.1f times two to the power of %d is %2.1f\n", x, p, y );  
}  
```  
  
## Ausgabe  
  
```  
4.0 times two to the power of 3 is 32.0  
```  
  
## .NET Framework-Entsprechung  
 [System::Math::Pow](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [Modf, Modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)