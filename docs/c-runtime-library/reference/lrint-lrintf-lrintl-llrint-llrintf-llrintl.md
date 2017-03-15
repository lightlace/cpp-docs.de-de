---
title: "Lrint, Lrintf, Lrintl, Llrint, Llrintf, llrintl | Microsoft Docs"
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
  - "lrint"
  - "lrintl"
  - "lrintf"
  - "llrint"
  - "llrintf"
  - "llrintl"
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
  - "lrint"
  - "lrintf"
  - "lrintl"
  - "llrint"
  - "llrintf"
  - "llrintl"
  - "math/lrint"
  - "math/lrintf"
  - "math/lrintl"
  - "math/llrint"
  - "math/llrintf"
  - "math/llrintl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lrint-Funktion"
  - "Lrintf-Funktion"
  - "Lrintl-Funktion"
  - "Llrint-Funktion"
  - "Llrintf-Funktion"
  - "Llrintl-Funktion"
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Lrint, Lrintf, Lrintl, Llrint, Llrintf, llrintl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rundet den angegebenen Gleitkommawert auf den nächsten ganzzahligen Wert mit dem aktuellen Rundungsmodus und Richtung.  
  
## Syntax  
  
```  
long int lrint(  
   double x  
);  
  
long int lrint(  
   float x  
); //C++ only  
  
long int lrint(  
   long double x  
); //C++ only  
  
long int lrintf(  
   float x  
);  
  
long int lrintl(  
   long double x  
);  
  
long long int llrint(  
   double x  
);  
  
long long int llrint(  
   float x  
); //C++ only  
  
long long int llrint(  
   long double x  
); //C++ only  
  
long long int llrintf(  
   float x  
);  
  
long long int llrintl(  
   long double x  
);  
  
```  
  
#### Parameter  
 \[in\] `x`  
 der zu rundende Wert.  
  
## Rückgabewert  
 Bei Erfolg gibt den gerundeten ganzzahligen Wert des `x`.  
  
|Problem|Zurück|  
|-------------|------------|  
|`x` liegt außerhalb des Bereichs des Rückgabetyps<br /><br /> `x` \= ±∞<br /><br /> `x` \= NaN|Löst FE\_INVALID aus und gibt 0 \(null\) zurück.|  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Aufrufen `lrint` und `llrint` dauern float\- und long double\-Typen. In einem C\-Programm `lrint` und `llrint` immer übernehmen einen Double\-Wert.  
  
 Wenn `x` nicht die entsprechende Gleitkommazahl darstellt eines ganzzahligen Werts, diese Funktionen lösen FE\_INEXACT.  
  
 **Microsoft\-spezifisch**: Wenn das Ergebnis außerhalb des Bereichs des Rückgabetyps ist oder wenn der Parameter ein NaN oder unendlich ist, ist der Rückgabewert Implementierung definiert. Der Microsoft\-Compiler gibt der Wert 0 \(null\) zurück.  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`lrint`, `lrintf`, `lrintl`, `llrint`, `llrintf`, `llrintl`|\<math.h\>|\<cmath\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)