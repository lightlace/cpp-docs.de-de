---
title: "srand"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "srand"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "srand"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Zahlen, Pseudozufällig"
  - "Zahlen, Zufällig"
  - "Pseudozufallszahlen"
  - "Zufallszahlen, Generieren"
  - "Zufälliger Startpunkt"
  - "Zufälliger Startpunkt, Festlegen"
  - "srand-Funktion"
  - "Startpunkte"
  - "Startpunkte, Festlegen zufälliger"
ms.assetid: 7bf56dc5-5692-4182-a3c1-18af98d2dd1a
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# srand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt den Startwert für den Pseudozufallszahlengenerator fest.  
  
## Syntax  
  
```  
void srand(  
   unsigned int seed   
);  
```  
  
#### Parameter  
 `seed`  
 Startwert für die Pseudozufallszahlengenerierung  
  
## Hinweise  
 Die `srand`\-Funktion legt den Ausgangspunkt für das Generieren von Pseudozufallsganzzahlen im aktuellen Thread fest.  Um den Generators zum Erzeugen derselben Sequenz von Ergebnissen erneut zu initialisieren, rufen Sie die `srand`\-Funktion auf, und verwenden Sie das gleiche `seed`\-Argument erneut.  Jeder andere Wert für `seed` legt den Generator in der Pseudozufallssequenz auf einen anderen Startpunkt fest.  `rand` ruft die generierten Pseudozufallszahlen ab.  Der Aufruf von `rand` vor irgendeinem Aufruf von `srand` generiert die gleiche Sequenz wie der Aufruf von `srand` mit `seed` übergeben als 1.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`srand`|\<stdlib.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Ein Beispiel hierfür finden Sie unter [rand](../../c-runtime-library/reference/rand.md).  
  
## .NET Framework-Entsprechung  
 [System::Random Class](https://msdn.microsoft.com/en-us/library/system.random.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [rand](../../c-runtime-library/reference/rand.md)