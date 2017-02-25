---
title: "_freea | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_freea"
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
apitype: "DLLExport"
f1_keywords: 
  - "freea"
  - "_freea"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_freea-Funktion"
  - "freea-Funktion"
  - "Speicherfreigabe"
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _freea
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt frei oder gibt einen Speicherblock freigegeben.  
  
## Syntax  
  
```  
void _freea(   
   void *memblock   
);  
```  
  
#### Parameter  
 `memblock`  
 Zuvor gemeinsam genutzt reservierter Speicherblock.  
  
## Rückgabewert  
 Keine.  
  
## Hinweise  
 Die `_freea` \- Funktion wird ein Speicherblock freigegeben \(`memblock`\) der zuvor durch einen Aufruf von [\_malloca](../../c-runtime-library/reference/malloca.md) zugeordnet wurde.  `_freea` überprüft, um festzustellen, ob der Speicher auf dem Heap oder dem Stapel zugeordnet wurde.  Wenn er auf dem Stapel zugeordnet wurde, hat `_freea` keine Auswirkungen.  Wenn er auf dem Heap zugeordnet wurde, ist die Anzahl der Bytes freigegebenen zur Anzahl Bytes angefordert äquivalent, als Block zugeordnet wurde.  Wenn `memblock``NULL` ist, wird der Zeiger ignoriert und `_freea` wird sofort zurückgegeben.  Der Versuch, einen ungültigen Zeiger \(einen Zeiger auf einen Speicherblock, der von `_malloca` nicht zugeordnet wurde\) freizugeben, folgende Zuordnungsanforderungen beeinflussen und verursacht möglicherweise Fehler.  
  
 \_`freea` ruft `free` intern auf, wenn es ermittelt, dass der Speicher auf dem Heap reserviert wird.  Ob der Speicher auf dem Heap oder Stapel befindet, wird von einem Markierung bestimmt, der in den Speicher an der Adresse direkt vor den reservierten Speicher abgelegt wird.  
  
 Wenn bei der Freigabe des Speichers ein Fehler auftritt, wird `errno` mit Informationen des Betriebssystems über die Art des Fehlers angegeben.  Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Nachdem ein Speicherblock freigegeben wurde, minimiert [\_heapmin](../../c-runtime-library/reference/heapmin.md) und der freie Arbeitsspeicher im Heap, indem die nicht verwendeten Bereiche Außerdem werden und sie wieder für das Betriebssystem frei.  Freigegebener Arbeitsspeicher, der nicht dem Betriebssystem verworfen wird, wird z freien Pool wiederhergestellt und zur Zuordnung wieder verfügbar.  
  
 Ein Aufruf von `_freea` muss alle Aufrufe von `_malloca` dargestellt.  Es ist auch ein Fehler, um `_freea` auf den gleichen Arbeitsspeicher zweimal aufruft.  Wenn die Anwendung mit einer Debugversion der C\-Laufzeitbibliotheken verknüpft wird, insbesondere mit [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)\-Funktionen aktiviert durch Definition von `_CRTDBG_MAP_ALLOC`, ist es einfacher, fehlende oder duplizierte Aufrufe `_freea` zu suchen.  Weitere Informationen dazu, wie der Heap während des Debuggingsprozesses verwaltet wird, finden Sie unter [Der CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `_freea` ist als `__declspec(noalias)` gekennzeichnet und bedeutet, dass die Funktion, die gewährleistet sind globale Variablen nicht zu ändern.  Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_freea`|\<stdlib.h\> und \<malloc.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Ein Beispiel hierfür finden Sie unter [\_malloca](../../c-runtime-library/reference/malloca.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [\_malloca](../../c-runtime-library/reference/malloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)