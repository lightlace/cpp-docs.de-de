---
title: "Ilogb, Ilogbf, ilogbl2 | Microsoft Docs"
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
  - "ilogb"
  - "ilogbf"
  - "ilogbl"
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
  - "ilogb"
  - "ilogbf"
  - "ilogbl"
  - "math/ilogb"
  - "math/ilogbf"
  - "math/ilogbl"
helpviewer_keywords: 
  - "ilogb-Funktion"
  - "ilogbf-Funktion"
  - "Ilogbl-Funktion"
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Ilogb, Ilogbf, ilogbl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft eine ganze Zahl, die den ausgewogene Base\-2\-Exponenten des angegebenen Werts darstellt.  
  
## Syntax  
  
```  
int ilogb(  
   double x  
);  
  
int ilogb(  
   float x  
); //C++ only  
  
int ilogb(  
   long double x  
); //C++ only  
  
int ilogbf(  
   float x  
);  
  
int ilogbl(  
   long double x  
);  
  
```  
  
#### Parameter  
 \[in\] `x`  
 Der angegebene Wert.  
  
## Rückgabewert  
 Im Erfolgsfall Zurückgeben der Exponent zur Basis\-2 `x` als eine signierte `int` Wert.  
  
 Andernfalls gibt die folgenden Werte, die in \< math.h \> definiert:  
  
|Eingabe|Ergebnis|  
|-------------|--------------|  
|±0|FP\_ILOGB0|  
|±INF, ±nan, unbestimmte|FP\_ILOGBNAN|  
  
 Fehler werden gemeldet, gemäß den Angaben in [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Aufrufen `ilogb` verwenden und Zurückgeben von float\- und long double\-Typen. In einem C\-Programm verwendet `ilogb` immer double und gibt auch double zurück.  
  
 Das Aufrufen dieser Funktion ist ähnlich wie das Aufrufen der entsprechenden `logb` \-Funktion und dann den zurückgegebenen Wert umwandeln `int`.  
  
## Anforderungen  
  
|Routine|C\-Header|C\+\+\-Header|  
|-------------|---------------|-------------------|  
|`ilogb`, `ilogbf`,  `ilogbl`|\<math.h\>|\<cmath\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [logb, logbf, logbl, \_logb, \_logbf](../../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)