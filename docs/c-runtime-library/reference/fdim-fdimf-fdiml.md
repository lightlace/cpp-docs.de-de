---
title: "Fdim, Fdimf, fdiml | Microsoft Docs"
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
  - "fdim"
  - "fdimf"
  - "fdiml"
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
  - "fdim"
  - "fdimf"
  - "fdiml"
  - "math/fdim"
  - "math/fdimf"
  - "math/fdiml"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fdim-Funktion"
  - "fdimf-Funktion"
  - "Fdiml-Funktion"
ms.assetid: 2d4ac639-51e9-462d-84ab-fb03b06971a0
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Fdim, Fdimf, fdiml
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt den positiven Unterschied zwischen den ersten und zweiten Wert.  
  
## Syntax  
  
```  
double fdim(  
   double x,   
   double y  
);  
  
float fdim(  
   float x,   
   float y  
); //C++ only  
  
long double fdim(  
   long double x,   
   long double y  
); //C++ only  
  
float fdimf(  
   float x,   
   float y  
);  
  
long double fdiml(  
   long double x,   
   long double y  
);  
  
```  
  
#### Parameter  
 \[in\] `x`  
 Der erste Wert.  
  
 \[in\] `y`  
 Der zweite Wert.  
  
## Rückgabewert  
 Gibt den positiven Unterschied zwischen `x` und `y`:  
  
|Rückgabewert|Szenario|  
|------------------|--------------|  
|X\-y|Wenn x \> y|  
|0|Wenn x \< \= y|  
  
 Andernfalls kann einer der folgenden Fehler zurückgegeben:  
  
|Problem|Zurück|  
|-------------|------------|  
|Überlauffehler\-Bereich|\+ HUGE\_VAL \+ HUGE\_VALF, oder \+ HUGE\_VALL|  
|Gleitkommaunterlauf verursachter Fehler|richtige Wert \(nach dem runden\)|  
|`x` oder `y` ist NaN|NaN|  
  
 Fehler werden gemeldet, gemäß den Angaben in [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Aufrufen `fdim` verwenden und Zurückgeben von float\- und long double\-Typen. In einem C\-Programm verwendet `fdim` immer double und gibt auch double zurück.  
  
 Diese Funktion entspricht, mit Ausnahme der Behandlung NaN [Fmax, Fmaxf, fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)\(`x`\-`y,` 0\).  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`fdim`, `fdimf`,  `fdiml`|\<math.h\>|\<cmath\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Fmax, Fmaxf, fmaxl](../../c-runtime-library/reference/fmax-fmaxf-fmaxl.md)   
 [Abs, Labs, Llabs, \_abs64](../../c-runtime-library/reference/abs-labs-llabs-abs64.md)