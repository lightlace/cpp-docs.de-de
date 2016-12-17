---
title: "free"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "free"
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
  - "free"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Speicherblöcke, Freigeben"
  - "free-Funktion"
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# free
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt frei oder gibt einen Speicherblock freigegeben.  
  
## Syntax  
  
```  
void free(   
   void *memblock   
);  
```  
  
#### Parameter  
 `memblock`  
 Zuvor gemeinsam genutzt reservierter Speicherblock.  
  
## Hinweise  
 Die `free`\-Funktion wird ein Speicherblock freigegeben \(`memblock`\) die vorher durch einen Aufruf `calloc`, `malloc` oder `realloc` zugeordnet wurde.  Die Anzahl von freigegebenen Bytes entspricht der Anzahl Bytes angefordert äquivalent, als Block zugeordnet wurde \(oder neu zugeordnet, im Fall von `realloc`\).  Wenn `memblock``NULL` ist, wird der Zeiger ignoriert und `free` wird sofort zurückgegeben.  Der Versuch, einen ungültigen Zeiger \(einen Zeiger auf einen Speicherblock, der nicht durch `calloc`, zugeordnet wurde mit `malloc` oder `realloc`\) freizugeben folgenden Zuordnungsanforderungen beeinflussen und verursacht möglicherweise Fehler.  
  
 Wenn bei der Freigabe des Speichers ein Fehler auftritt, wird `errno` mit Informationen des Betriebssystems über die Art des Fehlers angegeben.  Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Nachdem ein Speicherblock freigegeben wurde, minimiert [\_heapmin](../../c-runtime-library/reference/heapmin.md) und der freie Arbeitsspeicher im Heap, indem die nicht verwendeten Bereiche Außerdem werden und sie wieder für das Betriebssystem frei.  Freigegebener Arbeitsspeicher, der nicht dem Betriebssystem verworfen wird, wird z freien Pool wiederhergestellt und zur Zuordnung wieder verfügbar.  
  
 Wenn die Anwendung mit einer Debugversion der C\-Laufzeitbibliotheken verknüpft ist, wird `free` von [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md) auf.  Weitere Informationen dazu, wie der Heap während des Debuggingsprozesses verwaltet wird, finden Sie unter [Der CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `free` ist als `__declspec(noalias)` gekennzeichnet und bedeutet, dass die Funktion, die gewährleistet sind globale Variablen nicht zu ändern.  Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).  
  
 Um dem Arbeitsspeicher freizugeben, der mit [\_malloca](../../c-runtime-library/reference/malloca.md) zugeordnet ist, verwenden Sie [\_freea](../../c-runtime-library/reference/freea.md).  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`free`|\<stdlib.h\> und \<malloc.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Im Beispiel für [malloc](../../c-runtime-library/reference/malloc.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [\_alloca](../../c-runtime-library/reference/alloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [\_freea](../../c-runtime-library/reference/freea.md)