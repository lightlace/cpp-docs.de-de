---
title: "log2, log2f, log2l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "log2"
  - "log2l"
  - "log2f"
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
dev_langs: 
  - "C++"
ms.assetid: 94d11b38-70b7-4d3a-94ac-523153c92b2e
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# log2, log2f, log2l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt den binären Logarithmus \(Basis 2\) der angegebene Wert.  
  
## Syntax  
  
```  
double log2(  
   double x  
);  
  
float log2(  
   float x  
); //C++ only  
  
long double log2(  
   long double x  
); //C++ only  
  
float log2f(  
   float x  
);  
  
long double log2l(  
   long double x  
);  
  
```  
  
#### Parameter  
 \[in\] `x`  
 Der Wert, der den Logarithmus zur Basis 2 zu bestimmen.  
  
## Rückgabewert  
 Bei Erfolg gibt log2 zurückgeben `x`.  
  
 Andernfalls kann die folgenden Werte zurück:  
  
|Problem|Zurück|  
|-------------|------------|  
|`x` \< 0|NaN|  
|`x` \= ±0|\-INFINITY|  
|`x` \= 1|\+0|  
|PLUS UNENDLICH|PLUS UNENDLICH|  
|NaN|NaN|  
|Domänenfehler|NaN|  
|pol\-Fehler|\-HUGE\_VAL, \-HUGE\_VALF, oder \- HUGE\_VALL|  
  
 Fehler werden gemeldet, gemäß den Angaben in [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Hinweise  
 Ist x eine ganze Zahl, gibt diese Funktion im Wesentlichen den nullbasierten Index des höchstwertigen Bits des 1 `x`.  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`log2`, `log2f`,  `log2l`|\<math.h\>|\<cmath\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [EXP2, exp2f, exp2l](../../c-runtime-library/reference/exp2-exp2f-exp2l.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)