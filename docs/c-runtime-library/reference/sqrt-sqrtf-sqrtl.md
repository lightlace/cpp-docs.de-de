---
title: "sqrt, sqrtf, sqrtl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "sqrtl"
  - "sqrtf"
  - "sqrt"
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
  - "sqrt"
  - "sqrtf"
  - "_sqrtl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_sqrtl-Funktion"
  - "Berechnen von Quadratwurzeln"
  - "sqrt-Funktion"
  - "sqrtf-Funktion"
  - "sqrtl-Funktion"
  - "Quadratwurzeln, Berechnen"
ms.assetid: 2ba9467b-f172-41dc-8f10-b86f68fa813c
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# sqrt, sqrtf, sqrtl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet die Quadratwurzel.  
  
## Syntax  
  
```  
double sqrt(    double x  ); float sqrt(    float x  );  // C++ only long double sqrt(    long double x );  // C++ only float sqrtf(    float x  ); long double sqrtl(    long double x  );  
```  
  
#### Parameter  
 `x`  
 Nicht negativer Gleitkommawert  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `sqrt` aufrufen, die `float` oder `long double`\-Typen verwenden und zurückgeben.  In einem C\-Programm verwendet `sqrt` immer `double` und gibt diesen Wert zurück.  
  
## Rückgabewert  
 Die `sqrt`\-Funktion gibt die Quadratwurzel von `x` zurück.  Wenn `x` negativ ist, gibt `sqrt` standardmäßig eine unendliche NaN zurück.  
  
|Eingabe|SEH\-Ausnahme|`_matherr`\-Ausnahme|  
|-------------|-------------------|--------------------------|  
|± QNAN,IND|Keine|\_DOMAIN|  
|\- ∞|Keine|\_DOMAIN|  
|x\<0|Keine|\_DOMAIN|  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`sqrt`, `sqrtf`, `sqrtl`|\<math.h\>|\<cmath\>|  
  
 Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_sqrt.c  
// This program calculates a square root.  
  
#include <math.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   double question = 45.35, answer;  
   answer = sqrt( question );  
   if( question < 0 )  
      printf( "Error: sqrt returns %f\n", answer );  
   else  
      printf( "The square root of %.2f is %.2f\n", question, answer );  
}  
```  
  
  **Die Quadratwurzel von 45,35 ist 6,732.**   
## .NET Framework-Entsprechung  
 [System::Math::Sqrt](https://msdn.microsoft.com/en-us/library/system.math.sqrt.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)   
 [pow, powf, powl](../../c-runtime-library/reference/pow-powf-powl.md)   
 [\_CIsqrt](../../c-runtime-library/cisqrt.md)