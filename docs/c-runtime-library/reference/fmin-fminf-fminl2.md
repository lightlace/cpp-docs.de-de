---
title: "Fmin, Fminf, fminl2 | Microsoft Docs"
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
  - "fmin"
  - "fminf"
  - "fminl"
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
  - "fmin"
  - "fminf"
  - "fminl"
  - "math/fmin"
  - "math/fminf"
  - "math/fminl"
helpviewer_keywords: 
  - "fmin-Funktion"
  - "fminf-Funktion"
  - "Fminl-Funktion"
ms.assetid: 1916dfb5-99c1-4b0d-aefb-513525c3f2ac
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Fmin, Fminf, fminl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt die kleinere von zwei angegebenen Werten.  
  
## Syntax  
  
```  
double fmin(  
   double x,   
   double y  
);  
  
float fmin(  
   float x,   
   float y  
); //C++ only  
  
long double fmin(  
   long double x,   
   long double y  
); //C++ only  
  
float fminf(  
   float x,   
   float y  
);  
  
long double fminl(  
   long double x,   
   long double y  
);  
  
```  
  
#### Parameter  
 `x`  
 Der erste zu vergleichende Wert.  
  
 `y`  
 Der zweite zu vergleichende Wert.  
  
## Rückgabewert  
 Bei erfolgreicher Ausführung gibt die kleinere von `x` oder `y`.  
  
|Eingabe|Ergebnis|  
|-------------|--------------|  
|`x` ist NaN|`y`|  
|`y` ist NaN|`x`|  
|`x` und `y` NaN sind|NaN|  
  
 Die Funktion nicht dazu, dass [\_matherr](../../c-runtime-library/reference/matherr.md) um aufgerufen werden, dazu führen, dass alle Ausnahmen, oder ändern Sie den Wert des `errno`.  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Aufrufen `fmin` verwenden und Zurückgeben von float\- und long double\-Typen. In einem C\-Programm verwendet `fmin` immer double und gibt auch double zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`fmin`, `fminf`,  `fminl`|C: \< math.h \><br /><br /> C\+\+: \< math.h \> oder \< Cmath \>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)