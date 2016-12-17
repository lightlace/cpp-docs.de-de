---
title: "FMA, Fmaf, fmal"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "fma"
  - "fmaf"
  - "fmal"
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
  - "fma"
  - "fmaf"
  - "fmal"
  - "math/fma"
  - "math/fmaf"
  - "math/fmal"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "fma-Funktion"
  - "fmaf-Funktion"
  - "Fmal-Funktion"
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# FMA, Fmaf, fmal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Multipliziert zwei Werte miteinander und dann rundet das Ergebnis, ohne alle Genauigkeitsverlust durch runden zwischengeschaltete einen dritten Wert hinzugefügt.  
  
## Syntax  
  
```  
double fma(  
   double x,   
   double y,   
   double z  
);  
  
float fma(  
   float  x,   
   float  y,   
   float z  
); //C++ only  
  
long double fma(  
   long double  x,   
   long double  y,   
   long double z  
); //C++ only  
  
float fmaf(  
   float  x,   
   float  y,   
   float z  
);  
  
long double fmal(  
   long double  x,   
   long double  y,   
   long double z  
);  
  
```  
  
#### Parameter  
 \[in\] `x`  
 Der erste zu multiplizierende Wert.  
  
 \[in\] `y`  
 Der zweite zu multiplizierende Wert.  
  
 \[in\] `z`  
 Der hinzuzufügende Wert.  
  
## Rückgabewert  
 Returns \(`x` ×    `y`\) \+ `z`. Der Rückgabewert wird mit dem aktuellen Rundung Format gerundet.  
  
 Andernfalls kann die folgenden Werte zurück:  
  
|Problem|Zurück|  
|-------------|------------|  
|`x` \= UNENDLICH, `y` \= 0 oder<br /><br /> `x` \= 0, `y` \= UNENDLICH|NaN|  
|`x` oder `y` \= genaue ± UNENDLICH, `z` \= UNENDLICH mit umgekehrtem Vorzeichen|NaN|  
|`x` oder `y` \= NaN|NaN|  
|keine \(`x` \= 0, `y`\= unbestimmte\) und `z` \= NaN<br /><br /> keine \(`x`undefiniert \= `y`\= 0\) und `z` \= NaN|NaN|  
|Überlauffehler\-Bereich|±HUGE\_VAL, ±HUGE\_VALF oder ±HUGE\_VALL|  
|Gleitkommaunterlauf verursachter Fehler|richtige Wert nach dem runden.|  
  
 Fehler werden gemeldet, gemäß den Angaben in [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Aufrufen `fma` verwenden und Zurückgeben von float\- und long double\-Typen. In einem C\-Programm verwendet `fma` immer double und gibt auch double zurück.  
  
 Diese Funktion berechnet den Wert, als ob er mit unendlicher Genauigkeit übernommen wurden, und dann das endgültige Ergebnis rundet.  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`fma`, `fmaf`,  `fmal`|\<math.h\>|\<cmath\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [remainder, remainderf, remainderl](../../c-runtime-library/reference/remainder-remainderf-remainderl.md)   
 [remquo, remquof, remquol](../../c-runtime-library/reference/remquo-remquof-remquol.md)