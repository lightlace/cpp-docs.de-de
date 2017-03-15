---
title: "lround, lroundf, lroundl, llround, llroundf, llroundl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "llround"
  - "llroundf"
  - "llroundl"
  - "lroundf"
  - "lround"
  - "lroundl"
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
  - "lround"
  - "lroundl"
  - "llroundl"
  - "llround"
  - "lroundf"
  - "llroundf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "llround-Funktion"
  - "llroundf-Funktion"
  - "llroundl-Funktion"
  - "lround-Funktion"
  - "lroundf-Funktion"
  - "lroundl-Funktion"
ms.assetid: cfb88a35-54c6-469f-85af-f7d695dcfdd8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# lround, lroundf, lroundl, llround, llroundf, llroundl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rundet einen Gleitkommawert auf die nächste Ganzzahl.  
  
## Syntax  
  
```  
long lround(   
   double x   
);  
long lround(  
   float x  
);  // C++ only  
long lround(  
   long double x  
);  // C++ only  
long lroundf(  
   float x  
);  
long lroundl(  
   long double x  
);  
long long llround(   
   double x   
);  
long long llround(  
   float x  
);  // C++ only  
long long llround(  
   long double x  
);  // C++ only  
long long llroundf(  
   float x  
);  
long long llroundl(  
   long double x  
);  
```  
  
#### Parameter  
 `x`  
 Der zu rundende Gleitkommawert.  
  
## Rückgabewert  
 Die Funktionen `lround` und `llround` geben die `long`\-Ganzzahl oder die `long long`\-Ganzzahl zurück, die `x` am nächsten liegt.  Halbe Werte werden kaufmännisch gerundet, unabhängig von der Einstellung des Gleitkomma\-Rundungsmodus.  Es gibt keine Fehlerrückgabe.  
  
|Eingabe|SEH\-Ausnahme|Matherr\-Ausnahme|  
|-------------|-------------------|-----------------------|  
|± `QNAN`, `IND`|Keine|`_DOMAIN`|  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `lround` oder `llround` aufrufen, die `float`\- und `long double`\-Werte verwenden und zurückgeben.  In einem C\-Programm verwenden `lround` und `llround` immer `double` und geben dieses auch zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`lround`, `lroundf`, `lroundl`, `llround`, `llroundf`, `llroundl`|\<math.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_lround.c  
// Build with: cl /W3 /Tc crt_lround.c  
// This example displays the rounded results of  
// the floating-point values 2.499999, -2.499999,   
// 2.8, -2.8, 3.5 and -3.5.  
  
#include <math.h>  
#include <stdio.h>  
  
int main( void )  
{  
   double x = 2.499999;  
   float y = 2.8f;  
   long double z = 3.5;  
  
   printf("lround(%f) is %d\n", x, lround(x));  
   printf("lround(%f) is %d\n", -x, lround(-x));  
   printf("lroundf(%f) is %d\n", y, lroundf(y));  
   printf("lroundf(%f) is %d\n", -y, lroundf(-y));  
   printf("lroundl(%Lf) is %d\n", z, lroundl(z));  
   printf("lroundl(%Lf) is %d\n", -z, lroundl(-z));  
}  
```  
  
  **lround\(2,499999\) ist 2**  
**lround\(– 2,499999\) ist – 2**  
**lroundf\(2,800000\) ist 3**  
**lroundf\(– 2,800000\) ist – 3**  
**lroundl\(2,500000\) ist 4**  
**lroundl\(– 2,500000\) ist – 4**   
## .NET Framework-Entsprechung  
 [System::Math::Round](https://msdn.microsoft.com/en-us/library/system.math.round.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [fmod, fmodf](../../c-runtime-library/reference/fmod-fmodf.md)   
 [lrint, lrintf, lrintl, llrint, llrintf, llrintl](assetId:///312fd869-a9c0-4107-bb23-ab8299d04385)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)   
 [nearbyint, nearbyintf, nearbyintl](assetId:///15111e73-331d-41d1-81b7-3e10df894848)   
 [rint, rintf, rintl](../../c-runtime-library/reference/rint-rintf-rintl.md)