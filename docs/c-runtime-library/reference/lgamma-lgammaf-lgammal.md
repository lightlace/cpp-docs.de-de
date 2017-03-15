---
title: "Lgamma, Lgammaf, lgammal | Microsoft Docs"
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
  - "lgamma"
  - "lgammaf"
  - "lgammal"
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
  - "lgamma"
  - "lgammaf"
  - "lgammal"
  - "math/lgamma"
  - "math/lgammaf"
  - "math/lgammal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lgamma-Funktion"
  - "Lgammal-Funktion"
  - "lgammaf-Funktion"
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Lgamma, Lgammaf, lgammal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt den natürlichen Logarithmus der Absolute Wert der Gammafunktion des angegebenen Werts.  
  
## Syntax  
  
```  
double lgamma(  
   double x  
);  
  
float lgamma(  
   float x  
); //C++ only  
  
long double lgamma(  
   long double x  
); //C++ only  
  
float lgammaf(  
   float x  
);  
  
long double lgammal(  
   long double x  
);  
  
```  
  
#### Parameter  
 \[in\] `x`  
 Der Wert berechnet.  
  
## Rückgabewert  
 Im Erfolgsfall Zurückgeben der natürliche Logarithmus des absoluten Werts der Gammafunktion von `x.`  
  
|Problem|Zurück|  
|-------------|------------|  
|`x` \= NaN|NaN|  
|`x` \= ±0|PLUS UNENDLICH|  
|`x`\= negative ganze Zahl|PLUS UNENDLICH|  
|±INFINITY|PLUS UNENDLICH|  
|pol\-Fehler|\+ HUGE\_VAL \+ HUGE\_VALF, oder \+ HUGE\_VALL|  
|Überlauffehler\-Bereich|±HUGE\_VAL, ±HUGE\_VALF oder ±HUGE\_VALL|  
  
 Fehler werden gemeldet, gemäß den Angaben in [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Aufrufen `lgamma` verwenden und Zurückgeben von float\- und long double\-Typen. In einem C\-Programm verwendet `lgamma` immer double und gibt auch double zurück.  
  
 Wenn x eine rationale Zahl ist, gibt diese Funktion den Logarithmus der Fakultät \(`x`\-1\).  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`lgamma`, `lgammaf`,  `lgammal`|\<math.h\>|\<cmath\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Tgamma, Tgammaf, tgammal](../../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)