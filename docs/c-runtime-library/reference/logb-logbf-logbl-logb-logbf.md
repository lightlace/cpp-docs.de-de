---
title: "logb, logbf, logbl, _logb, _logbf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "logb"
  - "_logb"
  - "_logbl"
  - "logbf"
  - "logbl"
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
  - "logb"
  - "logbl"
  - "_logb"
  - "_logbf"
  - "logbf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_logb-Funktion"
  - "_logbf-Funktion"
  - "Exponent, Gleitkommazahlen"
  - "Exponenten und Mantissen"
  - "Gleitkommafunktionen"
  - "Gleitkommafunktionen, Mantissen und Exponenten"
  - "logb-Funktion"
  - "logbf-Funktion"
  - "logbl-Funktion"
  - "Mantissen, Gleitkommavariablen"
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# logb, logbf, logbl, _logb, _logbf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Extrahiert den Exponentenwert eines Gleitkommaarguments.  
  
## Syntax  
  
```  
double logb(  
   double x   
);  
float logb(  
   float x   
); // C++ only  
long double logb(  
   long double x   
); // C++ only   
float logbf(  
   float x   
);  
long double logbl(  
   long double x   
);  
double _logb(  
   double x   
);  
float _logbf(  
   float x   
);  
```  
  
#### Parameter  
 x  
 Ein Gleitkommawert.  
  
## Rückgabewert  
 `logb` gibt den zufälligen Exponentenwert von `x` als ganze Zahl mit Vorzeichen zurück, dargestellt als Gleitkommawert.  
  
## Hinweise  
 Die `logb`\-Funktionen extrahieren den Exponentialwert des Gleitkommaarguments `x` so, als dass `x` mit unbegrenztem Bereich dargestellt würde.  Ein denormalisiertes Argument `x` wird wie ein normalisiertes behandelt.  
  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von `logb` aufrufen, die `float` oder `long double`\-Werte verwenden und zurückgeben.  In einem C\-Programm verwendet `logb` immer `double` und gibt diesen Wert zurück.  
  
|Eingabe|SEH\-Ausnahme|Matherr\-Ausnahme|  
|-------------|-------------------|-----------------------|  
|± QNAN,IND|Kein|\_DOMAIN|  
|± 0|ZERODIVIDE|\_SING|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_logb`|\<float.h\>|  
|`logb`, `logbf`, `logbl`, `_logbf`|\<math.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)