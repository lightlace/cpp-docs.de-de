---
title: free | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: free
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
f1_keywords: free
dev_langs: C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1be3f7141a8483aa7b0d43195b08506691e34fe3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="free"></a>free
Hebt die Zuweisung eines Speicherblocks auf oder gibt diesen frei.  
  
## <a name="syntax"></a>Syntax  
  
```  
void free(   
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `memblock`  
 Zuvor zugewiesener Speicherblock, der freigegeben werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `free` gibt einen Speicherblock frei (`memblock`), der zuvor durch einen Aufruf von `calloc`, `malloc` oder `realloc` belegt wurde. Die Anzahl der freigegebenen Bytes entspricht der Anzahl der Bytes, die angefordert wurden, als der Block belegt (oder mit `realloc` neu belegt) wurde. Wenn `memblock` `NULL` ist, wird der Zeiger ignoriert und `free` springt sofort zurück. Der Versuch, einen ungültigen Zeiger freizugeben (einen Zeiger auf einen Speicherblock, der nicht von `calloc`, `malloc`, oder `realloc` belegt wurde), kann nachfolgende Zuordnungsanforderungen beeinflussen und Fehler verursachen.  
  
 Wenn bei der Freigabe des Speichers ein Fehler auftritt, wird `errno` mit Informationen des Betriebssystems über die Art des Fehlers angegeben. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Nachdem ein Speicherblock freigegeben wurde, minimiert [_heapmin](../../c-runtime-library/reference/heapmin.md) die Menge des freien Speicherplatzes auf dem Heap, indem die nicht verwendeten Bereiche zusammengefügt und wieder an das Betriebssystem freigegeben werden. Freigegebener Speicher, der nicht an das Betriebssystem freigegeben wird, wird im freien Pool wiederhergestellt und ist wieder für eine Zuordnung verfügbar.  
  
 Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist, wird `free` nach [_free_dbg](../../c-runtime-library/reference/free-dbg.md) aufgelöst. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
 `free` ist als `__declspec(noalias)` gekennzeichnet, d.h., die Funktion ändert auf keinen Fall globale Variablen. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md).  
  
 Um Speicher mit [_malloca](../../c-runtime-library/reference/malloca.md) freizugeben, verwenden Sie [_freea](../../c-runtime-library/reference/freea.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`free`|\<stdlib.h> und \<malloc.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [malloc](../../c-runtime-library/reference/malloc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Memory Allocation (Speicherreservierung)](../../c-runtime-library/memory-allocation.md)   
 [_alloca](../../c-runtime-library/reference/alloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_free_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_freea](../../c-runtime-library/reference/freea.md)