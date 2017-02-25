---
title: "erf, erff, erfl, erfc, erfcf, erfcl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "erff"
  - "erfl"
  - "erf"
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
  - "erfl"
  - "erf"
  - "erff"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erf-Funktion"
  - "erff-Funktion"
  - "erfl-Funktion"
ms.assetid: 144d90d3-e437-41c2-a659-cd57596023b5
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# erf, erff, erfl, erfc, erfcf, erfcl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Berechnet die Fehlerfunktion oder die komplementäre Fehlerfunktion eines Werts.  
  
## Syntax  
  
```  
double erf(    double x ); float erf(    float x ); // C++ only long double erf(    long double x ); // C++ only float erff(    float x ); long double erfl(    long double x ); double erfc(    double x ); float erfc(    float x ); // C++ only long double erfc(    long double x ); // C++ only float erfcf(    float x ); long double erfcl(    long double x );  
```  
  
#### Parameter  
 `x`  
 Ein Gleitkommawert.  
  
## Rückgabewert  
 Die `erf`\-Funktionen geben die Gauß\-Fehlerfunktion von `x` zurück.  Die `erfc`\-Funktionen geben die komplementäre Gauß\-Fehlerfunktion von `x` zurück.  
  
## Hinweise  
 Die `erf`\-Funktionen berechnen die Gauß\-Fehlerfunktion von x, die wie folgt definiert ist:  
  
 ![Die Fehlerfunktion von x](../../c-runtime-library/reference/media/crt_erf_formula.png "CRT\_erf\_formula")  
  
 Die komplementäre Gauß\-Fehlerfunktion ist als 1 \- erf\(x\) definiert.  Die `erf`\-Funktionen geben einen Wert im Bereich \-1,0 bis 1,0 zurück.  Es gibt keine Fehlerrückgabe.  Die `erfc`\-Funktionen geben einen Wert im Bereich 0 bis 2 zurück.  Wenn `x` für `erfc` zu groß ist, wird die `errno`\-Variable auf `ERANGE` festgelegt.  
  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `erf` und `erfc` aufrufen, die `float`\- und `long double`\-Typen verwenden und zurückgeben.  In einem C\-Programm verwenden `erf` und `erfc` immer `double` und geben dieses auch zurück.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`erf`, `erff`, `erfl`, `erfc`, `erfcf`, `erfcl`|\<math.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)