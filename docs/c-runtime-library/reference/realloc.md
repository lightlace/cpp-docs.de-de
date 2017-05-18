---
title: realloc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- realloc
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _brealloc
- _nrealloc
- realloc
- _frealloc
dev_langs:
- C++
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: a3612dfc9906b23bd3581729fd1de53212fb4b1a
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="realloc"></a>realloc
Neubelegung von Arbeitsspeicherblöcken.  
  
## <a name="syntax"></a>Syntax  
  
```  
void *realloc(  
   void *memblock,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `memblock`  
 Zeiger zum vorherigen belegten Speicherblock.  
  
 `size`  
 Neue Größe in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `realloc` gibt einen `void`-Zeiger auf den neu belegten (und möglicherweise verschobenen) Speicherblock zurück.  
  
 Wenn nicht genügend Arbeitsspeicher verfügbar ist, um den Block auf die vorgegebene Größe auszudehnen, bleibt der ursprüngliche Block unverändert, und `NULL` wird zurückgegeben.  
  
 Wenn `size` 0 ist, wird der Block, auf den durch `memblock` gezeigt wird, freigegeben; der Rückgabewert ist `NULL`, und `memblock` zeigt auf den freigegebenen Block.  
  
 Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einen anderen Typ als `void` zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
## <a name="remarks"></a>Hinweise  
 Die `realloc`-Funktion ändert die Größe eines zugeordneten Speicherblocks. Das `memblock`-Argument zeigt auf den Anfang des Speicherblocks. Wenn `memblock` `NULL` ist, dann verhält sich `realloc` genauso wie `malloc` und weist einen neuen Block an `size`-Bytes zu. Wenn `memblock` nicht `NULL` ist, wird ein Zeiger von einem vorherigen Aufruf an `calloc`, `malloc` oder `realloc` zurückgegeben.  
  
 Das `size`-Argument gibt die neue Größe des Blocks in Bytes an. Der Inhalt des Blocks bleibt bis zum Minimum von neuer und alter Größe unverändert, obwohl sich der neue Block an einem anderen Speicherort befinden kann. Da der neue Block an einem neuen Speicherort liegen kann, kann nicht garantiert werden, dass der von `realloc` zurückgegebene Zeiger mit dem durch das `memblock`-Argument übergebenen Zeiger identisch ist. Falls der Puffer vergrößert wird, stellt `realloc` nicht sicher, dass der neu belegte Arbeitsspeicher mit 0 belegt ist.  
  
 `realloc` setzt `errno` auf `ENOMEM`, wenn eine Speicherbelegung fehlschlägt oder wenn der benötigte Speicherplatz größer als `_HEAP_MAXREQ` ist. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `realloc` ruft `malloc` auf, um mithilfe der C++-Funktion [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) den neuen Handlermodus festzulegen. Der neue Handlermodus gibt an, ob bei einem Fehler die neue Handlerroutine von `malloc` aufgerufen werden soll, wie dies von [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) festgelegt ist. Standardmäßig ruft `malloc` bei einem Speicherbelegungsfehler nicht die neue Handlerroutine auf. Sie können dieses Standardverhalten überschreiben, sodass, wenn `realloc` Speicher nicht belegen kann,`malloc` die neue Handlerroutine genauso aufruft wie der `new`-Operator, wenn dieser aus demselben Grund fehlschlägt. Um den Standardwert zu überschreiben, rufen Sie  
  
```  
_set_new_mode(1)  
```  
  
 rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit NEWMODE.OBJ (siehe [Linkoptionen](../../c-runtime-library/link-options.md)) her.  
  
 Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist, wird `realloc` in [_realloc_dbg](../../c-runtime-library/reference/realloc-dbg.md) aufgelöst. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
 `realloc` ist als `__declspec(noalias)` und `__declspec(restrict)` gekennzeichnet, das bedeutet, dass die Funktion globale Variablen definitiv nicht ändert und dass der zurückgegebene Zeiger keinen Alias hat. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`realloc`|\<stdlib.h> und \<malloc.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
Size of block after malloc of 1000 longs: 4000  
Size of block after realloc of 1000 more longs: 8000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)
