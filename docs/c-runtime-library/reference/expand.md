---
title: "_expand | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_expand"
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
  - "_bexpand"
  - "fexpand"
  - "expand"
  - "nexpand"
  - "_fexpand"
  - "_nexpand"
  - "bexpand"
  - "_expand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_expand-Funktion"
  - "expand-Funktion"
  - "Speicherblöcke, Ändern der Größe"
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _expand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert die Größe eines Speicherblocks.  
  
## Syntax  
  
```  
void *_expand(   
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
 `_expand` gibt ein void\-Zeiger zum neu belegten Speicherblock zurück.  `_expand`, außer `realloc`, kann einen Block nicht verschieben, um die Größe zu ändern.  Wenn genügend Arbeitsspeicher vorhanden ist, der den Block, zu erweitern ist verfügbar, ohne es zu verschieben, wird der Parameter `memblock` in `_expand` dem Rückgabewert.  
  
 `_expand` gibt `NULL` zurück, wenn ein Fehler während des Vorgangs erkannt wird.  Wenn `_expand` verwendet wird, um einen Speicherblock verkleinert wird, hat er möglicherweise Beschädigung im kleinen Blocksheap oder ein ungültiger Blockszeiger und geben `NULL` zurück.  
  
 Wenn nicht genügend Arbeitsspeicher vorhanden ist, der den Block, der angegebenen Größe zu erweitern ist verfügbar, ohne sie zu verschieben, wird `NULL` zurückgegeben.  `_expand` gibt nie einem Block zurück, der in eine Größe als kleiner angefordert erweitert wird.  Wenn ein Fehler auftritt, gibt `errno` die Art des Fehlers an.  Weitere Informationen zu `errno` finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Der Rückgabewert zeigt auf einem Speicherplatz, der garantiert wird, zum Speichern eines beliebigen Typs Objekt ordnungsgemäß ausgerichtet sind.  Um die neue Größe des Elements zu überprüfen, verwenden Sie `_msize`.  Um einen Zeiger auf einen anderen Typ als `void` zu erhalten, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
## Hinweise  
 Die `_expand`\-Funktion änder die Größe eines zuvor reservierten Speicherblocks durch den Versuch, Vertrag Block zu erweitern oder abzuschließen, ohne seinen Speicherort im Heap zu verschieben.  Der `memblock`\-Parameter zeigt auf den Anfang des Blocks.  Der `size`\-Parameter gibt die neue Größe des Blocks, in Bytes.  Der Inhalt des Blocks entspricht z kürzeren der neuen und den alten Größen unverändert.  `memblock` sollte kein Block liegen, der freigegeben wurde.  
  
> [!NOTE]
>  Auf 64\-Bit\-Plattformen keiner `_expand` möglicherweise nicht Vertrag Blocks, wenn die neue Größe kleiner ist, wenn die aktuelle Größe ab; insbesondere wenn der Block kleiner als 16K an Größe und daher in der Fragmentierungs\-Heap zugeordnet wurde, schlägt `_expand` den Block unverändert und gibt `memblock` zurück.  
  
 Wenn die Anwendung mit einer Debugversion der C\-Laufzeitbibliotheken verknüpft ist, wird `_expand` von [\_expand\_dbg](../../c-runtime-library/reference/expand-dbg.md) auf.  Weitere Informationen dazu, wie der Heap während des Debuggingsprozesses verwaltet wird, finden Sie unter [Der CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `memblock` ein NULL\-Zeiger befindet, wird von dieser Funktion ein ungültiger Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL` zurück.  Wenn `size` größer als `_HEAP_MAXREQ` ist, wird `errno` auf `ENOMEM` festgelegt und die Funktion gibt `NULL` zurück.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_expand`|\<malloc.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_expand.c  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char *bufchar;  
   printf( "Allocate a 512 element buffer\n" );  
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )  
      exit( 1 );  
   printf( "Allocated %d bytes at %Fp\n",   
         _msize( bufchar ), (void *)bufchar );  
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )  
      printf( "Can't expand" );  
   else  
      printf( "Expanded block to %d bytes at %Fp\n",   
            _msize( bufchar ), (void *)bufchar );  
   // Free memory   
   free( bufchar );  
   exit( 0 );  
}  
```  
  
  **Reservieren Sie eine Puffergröße mit 512 Elementen zu**  
**Zugeordnet 512 Bytes an 002C12BC**  
**Erweiterter Block zu 1024 Bytes an 002C12BC**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_msize](../../c-runtime-library/reference/msize.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)