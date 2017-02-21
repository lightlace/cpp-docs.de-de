---
title: "Nearbyint, Nearbyintf, nearbyintl1 | Microsoft Docs"
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
  - "nearbyint"
  - "nearbyintf"
  - "nerabyintl"
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
  - "nearbyint"
  - "nearbyintf"
  - "nearbyintl"
  - "math/nearbyint"
  - "math/narbyintf"
  - "math/narbyintl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nearbyint-Funktion"
  - "nearbyintf-Funktion"
  - "Nearbyintl-Funktion"
ms.assetid: dd39cb68-96b0-434b-820f-6ff2ea65584f
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Nearbyint, Nearbyintf, nearbyintl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rundet den angegebenen Gleitkommawert in eine ganze Zahl und gibt den Wert in einem Gleitkomma\-Format.  
  
## Syntax  
  
```  
double nearbyint(  
   double x  
);  
  
float nearbyint(  
   float x  
); //C++ only  
  
long double nearbyint(  
   long double x  
); //C++ only  
  
float nearbyintf(  
   float x  
);  
  
long double nearbyintl(  
   long double x  
);  
  
```  
  
#### Parameter  
 \[in\] `x`  
 Der zu rundende Wert.  
  
## Rückgabewert  
 Bei erfolgreicher Ausführung gibt `x`, gerundet auf die nächste ganze Zahl, mit der aktuellen Rundung Format wie Fegetround definiert. Andernfalls kann die Funktion einen der folgenden Werte zurück:  
  
|Problem|Zurück|  
|-------------|------------|  
|`x` ±INFINITY \=|±Infinity, unverändert|  
|`x` \= ±0|±0, unverändert|  
|`x` \= NaN|NaN|  
  
 Fehler werden nicht gemeldet, über [\_matherr](../../c-runtime-library/reference/matherr.md)insbesondere meldet diese Funktion nicht FE\_INEXACT Ausnahmen.  
  
## Hinweise  
 Der Hauptunterschied zwischen dieser Funktion und `rint` besteht darin, dass diese Funktion keine der ungenau Gleitkomma\-Ausnahme ausgelöst wird.  
  
 Da die maximale Gleitkommawerte genaue Ganzzahlen sind, wird diese Funktion selbst nie überlaufen; Stattdessen kann die Ausgabe den Rückgabewert überlaufen, abhängig von der, den Version der Funktion, die Sie verwenden.  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`nearbyint`, `nearbyintf`,  `nearbyintl`|\<math.h\>|\<cmath\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)