---
title: "realloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "realloc"
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
  - "_brealloc"
  - "_nrealloc"
  - "realloc"
  - "_frealloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_brealloc-Funktion"
  - "realloc-Funktion"
  - "nrealloc-Funktion"
  - "frealloc-Funktion"
  - "_nrealloc-Funktion"
  - "Arbeitsspeicherblöcke, Neuzuordnen"
  - "Arbeitsspeicher, Neuzuordnen"
  - "_frealloc-Funktion"
  - "Neuzuordnung von Arbeitsspeicherblöcken"
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# realloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zuordnen Speicherblöcke neu zu.  
  
## Syntax  
  
```  
void *realloc(  
   void *memblock,  
   size_t size   
);  
```  
  
#### Parameter  
 `memblock`  
 Zeiger zuvor dem reservierten Speicherblock.  
  
 `size`  
 Neue Größe in Bytes.  
  
## Rückgabewert  
 `realloc` gibt ein `void` Zeiger auf das neu zugeordnete \(und möglicherweise bewegt\) Speicherblock zurück.  
  
 Falls nicht genügend verfügbarer Speicher gibt, z des Blocks der angegebenen Größe zu erweitern, ist der erste Block unverändert gelassen, und `NULL` wird zurückgegeben.  
  
 Wenn `size` null ist, wird der Block, auf den durch `memblock` gezeigt wird, freigegeben; der Rückgabewert ist `NULL` und `memblock` ist Left, an einem freigegebenen Block selbst zu zeigen.  
  
 Der Rückgabewert zeigt auf einem Speicherplatz, der garantiert wird, zum Speichern eines beliebigen Typs Objekt ordnungsgemäß ausgerichtet sind.  Um einen Zeiger auf einen anderen Typ als `void` zu erhalten, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
## Hinweise  
 Die `realloc`\-Funktion änder die Größe eines reservierten Speicherblocks.  Das Argument `memblock` zeigt auf den Anfang des Speicherblocks.  Wenn `memblock``NULL` ist, verhält sich genauso wie `realloc` und `malloc` ordnet einem neuen Block `size` Bytes zu.  Wenn `memblock` nicht `NULL` ist, sollte ein Zeiger sein, der bei einem vorherigen Aufruf von `calloc`, `malloc` oder `realloc` zurückgegeben wird.  
  
 Das Argument `size` gibt die neue Größe des Blocks, in Bytes.  Der Inhalt des Blocks entspricht z kürzeren der neuen und den alten Größen unverändert, obwohl der neue Block in einem anderen Speicherort befinden kann.  Da der neue Block in einer neuen Speicherort sein kann, wird der Zeiger, der von `realloc` zurückgegeben wird, nicht gewährleistet, dass sich der Zeiger zu sein, der vom `memblock`\-Argument übergeben wird.  `realloc` stellt nicht neu belegte Arbeitsspeicher bei Auslösung im Fall von Pufferzunahme auf Null ein.  
  
 `realloc` wird `errno` auf `ENOMEM` fest, wenn die Speicherbelegung fehlschlägt, oder wenn der angeforderte Arbeitsspeicher `_HEAP_MAXREQ` überschreitet.  Informationen hierzu und andere Fehlercodes, finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `realloc` Ruft `malloc` um die Funktion der [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) verwenden, um den neuen Handlermodus festzulegen.  Der neue Handlermodus gibt an, ob bei einem Fehler `malloc` die neue Handlerroutine aufgerufen werden soll, wie dies von [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md) festgelegt ist.  Standardmäßig ruft `malloc` bei einem Speicherbelegungsfehler nicht die neue Handlerroutine auf.  Sie können dieses Standardverhalten überschreiben, sodass, wenn `realloc` Speicher nicht belegen kann,`malloc` die neue Handlerroutine genauso aufruft wie der `new`\-Operator, wenn dieser aus demselben Grund fehlschlägt.  Um den Standardwert zu überschreiben, rufen Sie  
  
```  
_set_new_mode(1)  
```  
  
 früh in ein Programm oder Link mit NEWMODE.OBJ \(siehe [Linkoptionen](../../c-runtime-library/link-options.md)\).  
  
 Wenn die Anwendung mit einer Debugversion der C\-Laufzeitbibliotheken verknüpft ist, wird `realloc` von [\_realloc\_dbg](../../c-runtime-library/reference/realloc-dbg.md) auf.  Weitere Informationen dazu, wie der Heap während des Debuggingsprozesses verwaltet wird, finden Sie unter [Der CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `realloc` ist als `__declspec(noalias)` gekennzeichnet und `__declspec(restrict)` heißt, dass die Funktion, die gewährleistet sind globale Variablen nicht zu ändern und der zurückgegebene Zeiger nicht von Alias\-.  Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [Einschränken ein](../../cpp/restrict.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`realloc`|\<stdlib.h\> und \<malloc.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_realloc.c  
// This program allocates a block of memory for  
// buffer and then uses _msize to display the size of that  
// block. Next, it uses realloc to expand the amount of  
// memory used by buffer and then calls _msize again to  
// display the new amount of memory allocated to buffer.  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   long *buffer, *oldbuffer;  
   size_t size;  
  
   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )  
      exit( 1 );  
  
   size = _msize( buffer );  
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );  
  
   // Reallocate and show new size:  
   oldbuffer = buffer;     // save pointer in case realloc fails  
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))   
        ==  NULL )  
   {  
      free( oldbuffer );  // free original block  
      exit( 1 );  
   }  
   size = _msize( buffer );  
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",   
            size );  
  
   free( buffer );  
   exit( 0 );  
}  
```  
  
  **Größe des Blockes nach von malloc 1000 long\-Werte: 4000**  
**Größe des Blockes nach realloc von 1000 Short Überlappung mehr: 8000**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)