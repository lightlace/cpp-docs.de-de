---
title: "Tgamma, Tgammaf, tgammal"
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
  - "tgamma"
  - "tgammaf"
  - "tgammal"
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
  - "tgamma"
  - "tgammaf"
  - "tgammal"
  - "math/tgamma"
  - "math/tgammaf"
  - "math/tgammal"
dev_langs: 
  - "C"
  - "C++"
helpviewer_keywords: 
  - "tgamma-Funktion"
  - "tgammaf-Funktion"
  - "Tgammal-Funktion"
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Tgamma, Tgammaf, tgammal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt die Gammafunktion des angegebenen Werts.  
  
## Syntax  
  
```  
double tgamma(  
   double x  
);  
  
float tgamma(  
   float x  
); //C++ only  
  
long double tgamma(  
   long double x  
); //C++ only  
  
float tgammaf(  
   float x  
);  
  
long double tgammal(  
   long double x  
);  
  
```  
  
#### Parameter  
 \[in\] `x`  
 Der Wert der Gammawert von gefunden.  
  
## Rückgabewert  
 Bei Erfolg gibt der Gammawert von `x`.  
  
 Ein Fehler kann auftreten, wenn die Größe der `x` ist zu groß oder zu klein für den Datentyp. Eine Domäne oder Bereichsfehler kann auftreten, wenn `x` \< \= 0.  
  
|Problem|Zurück|  
|-------------|------------|  
|X \= ±0|±INFINITY|  
|X \= negative ganze Zahl|NaN|  
|X \= \- UNENDLICH|NaN|  
|x \= Plus UNENDLICH|PLUS UNENDLICH|  
|X \= NaN|NaN|  
|Domänenfehler|NaN|  
|pol\-Fehler|±HUGE\_VAL, ±HUGE\_VALF oder ±HUGE\_VALL|  
|Überlauffehler\-Bereich|±HUGE\_VAL, ±HUGE\_VALF oder ±HUGE\_VALL|  
|Gleitkommaunterlauf verursachter Fehler|der richtige Wert nach dem runden.|  
  
 Fehler werden gemeldet, gemäß den Angaben in [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Tgamma aufrufen, die entgegennehmen und Zurückgeben von float\- und long double\-Typen. In einem C\-Programm Tgamma immer Double und gibt einen Double\-Wert zurück.  
  
 Wenn x eine natürliche Zahl ist, gibt diese Funktion die Fakultät \(x\-1\) zurück.  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`tgamma`, `tgammaf`,  `tgammal`|\<math.h\>|\<cmath\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [Lgamma, Lgammaf, lgammal](../../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)