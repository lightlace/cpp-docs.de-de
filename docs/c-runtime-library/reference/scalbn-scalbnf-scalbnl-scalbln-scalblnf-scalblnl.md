---
title: "scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl"
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
  - "scalblnl"
  - "scalbnl"
  - "scalbnf"
  - "scalblnf"
  - "scalbn"
  - "scalbln"
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
  - "scalblnf"
  - "scalbnl"
  - "scalblnl"
  - "scalbln"
  - "scalbn"
  - "scalbnf"
dev_langs: 
  - "C++"
ms.assetid: df2f1543-8e39-4af4-a5cf-29307e64807d
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# scalbn, scalbnf, scalbnl, scalbln, scalblnf, scalblnl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Multipliziert eine Gleitkommazahl mit einer ganzzahligen Potenz von FLT\_RADIX.  
  
## Syntax  
  
```  
double scalbn(    double x,    int exp  ); float scalbn(    float x,    int exp );  // C++ only long double scalbn(    long double x,    int exp );  // C++ only  float scalbnf(    float x,    int exp );  long double scalbnl(    long double x,    int exp ); double scalbln(    double x,    long exp  ); float scalbln(    float x,    long exp );  // C++ only long double scalbln(    long double x,    long exp );  // C++ only  float scalblnf(    float x,    long exp );  long double scalblnl(    long double x,    long exp );  
```  
  
#### Parameter  
 `x`  
 Gleitkommawert.  
  
 `exp`  
 Ganzzahlexponent.  
  
## Rückgabewert  
 Bei Erfolg gibt die `scalbn`\-Funktion den Wert von `x` \* `FLT_RADIX`<sup>exp</sup> zurück.  Bei einem Überlauf und abhängig vom Vorzeichen von `x`, gibt `scalbn` \+\/– `HUGE_VAL` zurück. Der `errno`\-Wert wird auf `ERANGE` gesetzt.  
  
 Weitere Informationen über `errno` und mögliche Fehlerrückgabewerte finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 `FLT_RADIX` ist in \<float.h\> als native Gleitkommabasis definiert; in binären Systemen hat es den Wert 2, und `scalbn` entspricht [ldexp](../../c-runtime-library/reference/ldexp.md).  
  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `scalbn` und `scalbln` aufrufen, die `float`\- oder `long double`\-Typen verwenden und zurückgeben.  In einem C\-Programm verwendet `scalbn` immer `double` und `int` und gibt `double` zurück, und `scalbln` verwendet immer `double` und `long` und gibt `double` zurück.  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`scalbn`, `scalbnf`, `scalbnl`, `scalbln`, `scalblnf`, `scalblnl`|\<math.h\>|\<cmath\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_scalbn.c  
// Compile using: cl /W4 crt_scalbn.c  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 6.4, y;  
   int p = 3;  
  
   y = scalbn( x, p );  
   printf( "%2.1f times FLT_RADIX to the power of %d is %2.1f\n", x, p, y );  
}  
```  
  
## Ausgabe  
  
```  
6.4 times FLT_RADIX to the power of 3 is 51.2  
```  
  
## .NET Framework-Entsprechung  
 [System::Math::Pow](https://msdn.microsoft.com/en-us/library/system.math.pow.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [ldexp](../../c-runtime-library/reference/ldexp.md)   
 [Modf, Modff, modfl](../../c-runtime-library/reference/modf-modff-modfl.md)