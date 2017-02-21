---
title: "_recalloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_recalloc"
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
  - "_recalloc"
  - "recalloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_recalloc-Funktion"
  - "recalloc-Funktion"
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# _recalloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Kombination von `realloc` und `calloc`.  Ordnet ein Array im Speicher neu zu und initialisiert ihre Elemente bis 0.  
  
## Syntax  
  
```  
void *_recalloc(   
   void *memblock  
   size_t num,  
   size_t size   
);  
```  
  
#### Parameter  
 `memblock`  
 Zeiger zuvor dem reservierten Speicherblock.  
  
 `num`  
 Anzahl der Elemente.  
  
 `size`  
 Länge in Bytes jedes Elements.  
  
## Rückgabewert  
 `_recalloc` gibt ein `void` Zeiger auf das neu zugeordnete \(und möglicherweise bewegt\) Speicherblock zurück.  
  
 Falls nicht genügend verfügbarer Speicher gibt, z des Blocks der angegebenen Größe zu erweitern, ist der erste Block unverändert gelassen, und `NULL` wird zurückgegeben.  
  
 Wenn die angeforderte Größe ist, wird der Block, auf den durch `memblock` gezeigt wird, freigegeben; der Rückgabewert ist `NULL` und `memblock` ist Left, an einem freigegebenen Block selbst zu zeigen.  
  
 Der Rückgabewert zeigt auf einem Speicherplatz, der garantiert wird, zum Speichern eines beliebigen Typs Objekt ordnungsgemäß ausgerichtet sind.  Um einen Zeiger auf einen anderen Typ als `void` zu erhalten, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
## Hinweise  
 Die \_`recalloc`\-Funktion änder die Größe eines reservierten Speicherblocks.  Das Argument `memblock` zeigt auf den Anfang des Speicherblocks.  Wenn `memblock``NULL` ist, ist das Übergabeverhalten \_`recalloc` genauso wie [calloc](../../c-runtime-library/reference/calloc.md) und ordnet einem neuen Block `num` \* `size` Bytes zu.  Jedes Element wird 0 initialisiert.  Wenn `memblock` nicht `NULL` ist, sollte ein Zeiger sein, der bei einem vorherigen Aufruf von `calloc`, von [malloc](../../c-runtime-library/reference/malloc.md) oder [realloc](../../c-runtime-library/reference/realloc.md) zurückgegeben wird.  
  
 Da der neue Block in einer neuen Speicherort sein kann, wird der Zeiger, der durch \_`recalloc` zurückgegeben wird, nicht gewährleistet, dass sich der Zeiger zu sein, der vom `memblock`\-Argument übergeben wird.  
  
 `_recalloc` wird `errno` auf `ENOMEM` fest, wenn die Speicherbelegung fehlschlägt, oder wenn der angeforderte Arbeitsspeicher `_HEAP_MAXREQ` überschreitet.  Informationen hierzu und andere Fehlercodes, finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `recalloc` Ruft `realloc` um die Funktion der [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) verwenden, um den neuen Handlermodus festzulegen.  Der neue Handlermodus gibt an, ob bei einem Fehler `realloc` die neue Handlerroutine aufgerufen werden soll, wie dies von [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md) festgelegt ist.  Standardmäßig ruft `realloc` bei einem Speicherbelegungsfehler nicht die neue Handlerroutine auf.  Sie können dieses Standardverhalten überschreiben, sodass, wenn \_`recalloc` Speicher belegen nicht, kann `realloc` die neue Handlerroutine genauso aufruft, dass der Operator `new` führt, die aus demselben Grund fehlschlägt.  Um den Standardwert zu überschreiben, rufen Sie  
  
```  
_set_new_mode(1)  
```  
  
 frühzeitig im Programm oder im Link mit NEWMODE.OBJ.  
  
 Wenn die Anwendung mit einer Debugversion der C\-Laufzeitbibliotheken verknüpft ist, ändert sich zu [\_recalloc\_dbg](../../c-runtime-library/reference/recalloc-dbg.md)\_`recalloc` auf.  Weitere Informationen dazu, wie der Heap während des Debuggingsprozesses verwaltet wird, finden Sie unter [Der CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `_recalloc` ist als `__declspec(noalias)` gekennzeichnet und `__declspec(restrict)` heißt, dass die Funktion, die gewährleistet sind globale Variablen nicht zu ändern und der zurückgegebene Zeiger nicht von Alias\-.  Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [Einschränken ein](../../cpp/restrict.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_recalloc`|\<stdlib.h\> und \<malloc.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [\_recalloc\_dbg](../../c-runtime-library/reference/recalloc-dbg.md)   
 [\_aligned\_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)   
 [\_aligned\_offset\_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [Linkoptionen](../../c-runtime-library/link-options.md)