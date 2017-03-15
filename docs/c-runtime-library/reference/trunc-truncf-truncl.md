---
title: "Trunc, Truncf, truncl | Microsoft Docs"
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
  - "trunc"
  - "truncf"
  - "truncl"
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
  - "trunc"
  - "truncf"
  - "truncl"
  - "math/trunc"
  - "math/truncf"
  - "math/truncl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "trunc-Funktion"
  - "truncf-Funktion"
  - "Truncl-Funktion"
ms.assetid: de2038ac-ac0b-483e-870c-e8992dcd4fd0
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Trunc, Truncf, truncl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt die nächste ganze Zahl, die kleiner oder gleich der angegebenen Gleitkommawert ist.  
  
## Syntax  
  
```  
double trunc(  
   double x  
);  
  
float trunc(  
   float x  
); //C++ only  
  
long double trunc(  
   long double x  
); //C++ only  
  
float trunc(  
   float x  
); //C++ only  
  
long double truncl(  
   long double x  
);  
  
```  
  
#### Parameter  
 \[in\] `x`  
 Der Wert abgeschnitten.  
  
## Rückgabewert  
 Bei erfolgreicher Ausführung gibt einen ganzzahligen Wert von `x`, in Richtung 0 \(null\) gerundet.  
  
 Andernfalls kann eine der folgenden zurück:  
  
|Problem|Zurück|  
|-------------|------------|  
|`x` ±INFINITY \=|w|  
|`x` \=  ±0|w|  
|`x` \= NaN|NaN|  
  
 Fehler werden gemeldet, gemäß den Angaben in [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Hinweise  
 Da C\+\+ das Überladen zulässt, können Sie Überladungen von Aufrufen `trunc` verwenden und Zurückgeben von float\- und long double\-Typen. In einem C\-Programm verwendet `trunc` immer double und gibt auch double zurück.  
  
 Da die größten Gleitkommawerte genaue Ganzzahlen sind, wird diese Funktion nicht eigenständig überlaufen. Allerdings kann die Funktion durch Rückgabe eines Werts in einen ganzzahligen Typ einen Überlauf verursachen.  
  
 Sie können sich auch abgerundet, durch Implizites Konvertieren von Gleitkommazahlen, ganzzahlige; Dies ist jedoch so nur die Werte, die in den Zieltyp gespeichert werden können.  
  
## Anforderungen  
  
|Funktion|C\-Header|C\+\+\-Header|  
|--------------|---------------|-------------------|  
|`trunc`, `truncf`,  `truncl`|\<math.h\>|\<cmath\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Siehe auch  
 [Alphabetische Funktionsreferenz](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [floor, floorf, floorl](../../c-runtime-library/reference/floor-floorf-floorl.md)   
 [ceil, ceilf, ceill](../../c-runtime-library/reference/ceil-ceilf-ceill.md)   
 [round, roundf, roundl](../../c-runtime-library/reference/round-roundf-roundl.md)