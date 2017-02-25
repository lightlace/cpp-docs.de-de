---
title: "_msize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_msize"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "msize"
  - "_msize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_msize-Funktion"
  - "Speicherblöcke"
  - "msize-Funktion"
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _msize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die Größe eines Speicherblocks zurück, der im Heap zugeordnet wird.  
  
## Syntax  
  
```  
  
      size_t _msize(  
   void *memblock   
);  
```  
  
#### Parameter  
 `memblock`  
 Zeiger zum Speicherblock.  
  
## Rückgabewert  
 `_msize` gibt die Größe \(in Bytes\) als ganze Zahl ohne Vorzeichen zurück.  
  
## Hinweise  
 Die Funktion `_msize` wird der Schriftgrad, in Bytes, des Speicherblocks zurück, der durch den Aufruf `calloc`, `malloc` oder `realloc` zugeordnet ist.  
  
 Wenn die Anwendung mit einer Debugversion der C\-Laufzeitbibliotheken verknüpft ist, wird `_msize` von [\_msize\_dbg](../../c-runtime-library/reference/msize-dbg.md) auf.  Weitere Informationen dazu, wie der Heap während des Debuggingsprozesses verwaltet wird, finden Sie unter [Der CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Diese Funktion überprüft seine Parameter.  Wenn `memblock` ein NULL\-Zeiger ist, ruft `_msize` einen Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn der Fehler behandelt wird, legt die Funktion `errno` auf `EINVAL` fest und gibt \-1 zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_msize`|\<malloc.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Im Beispiel für [realloc](../../c-runtime-library/reference/realloc.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [\_expand](../../c-runtime-library/reference/expand.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)