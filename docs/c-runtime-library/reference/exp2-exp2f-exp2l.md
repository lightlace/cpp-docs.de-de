---
title: "EXP2, exp2f, exp2l | Microsoft Docs"
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
  - "exp2"
  - "exp2f"
  - "exp2l"
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
  - "exp2"
  - "math/exp2"
  - "exp2f"
  - "math/exp2f"
  - "exp2l"
  - "math/exp2l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exp2-Funktion"
  - "exp2f-Funktion"
  - "exp2l-Funktion"
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# EXP2, exp2f, exp2l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wird ausgelöst, auf den angegebenen Wert \(z. B. 2ˣ\) 2 berechnet.  
  
## Syntax  
  
```  
double exp2(  
   double x  
);  
  
float exp2(  
   float x  
);  // C++ only  
  
long double exp2(  
   long double x  
); // C++ only  
  
float exp2f(  
   float x  
);  
  
long double exp2l(  
   long double x  
);  
  
```  
  
#### Parameter  
 \[in\] `x`  
 Der Wert des Exponenten.  
  
## Rückgabewert  
 Bei Erfolg gibt der Exponent zur Basis\-2 `x` \(2ˣ\). Andernfalls kann die folgenden Werte zurück:  
  
|Problem|Zurück|  
|-------------|------------|  
|`x` \= ±0|1|  
|`x` \= \- UNENDLICH|\+0|  
|`x` \= PLUS UNENDLICH|PLUS UNENDLICH|  
|`x` \= NaN|NaN|  
|Überlauffehler\-Bereich|\+ HUGE\_VAL \+ HUGE\_VALF, oder \+ HUGE\_VALL|  
|Gleitkommaunterlauf verursachter Fehler|korrekte Ergebnis, nach dem runden|  
  
 Fehler werden gemeldet, gemäß den Angaben in [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Aufrufen `exp2` verwenden und Zurückgeben von float\- und long double\-Typen. In einem C\-Programm verwendet `exp2` immer double und gibt auch double zurück.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`exp`, `expf`, `expl`|\<math.h\>|\<cmath\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp, expf](../../c-runtime-library/reference/exp-expf.md)   
 [log2, log2f, log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)