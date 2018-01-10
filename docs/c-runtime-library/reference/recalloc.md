---
title: _recalloc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _recalloc
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
- _recalloc
- recalloc
dev_langs: C++
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d1f6052e71746bb05701e0d34f10585d5533be4e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recalloc"></a>_recalloc
Die Kombination aus `realloc` und `calloc`. Ordnet ein Array im Speicher neu zu und initialisiert seine Elemente auf 0.  
  
## <a name="syntax"></a>Syntax  
  
```  
void *_recalloc(   
   void *memblock  
   size_t num,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `memblock`  
 Zeiger zum vorherigen belegten Speicherblock.  
  
 `num`  
 Anzahl der Elemente.  
  
 `size`  
 Länge jedes Elements in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `_recalloc` gibt einen `void`-Zeiger auf den neu belegten (und möglicherweise verschobenen) Speicherblock zurück.  
  
 Wenn nicht genügend Arbeitsspeicher verfügbar ist, um den Block auf die vorgegebene Größe auszudehnen, bleibt der ursprüngliche Block unverändert, und `NULL` wird zurückgegeben.  
  
 Wenn die angeforderte Größe 0 beträgt, wird der Block, auf den durch `memblock` gezeigt wird, freigegeben; der Rückgabewert beträgt `NULL` und `memblock` zeigt auf den freigegebenen Block.  
  
 Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einen anderen Typ als `void` zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
## <a name="remarks"></a>Hinweise  
 Die `_recalloc`-Funktion ändert die Größe eines zugeordneten Speicherblocks. Das `memblock`-Argument zeigt auf den Anfang des Speicherblocks. Wenn `memblock` ist `NULL`, `_recalloc` verhält sich genauso wie [Calloc](../../c-runtime-library/reference/calloc.md) und ordnet einen neuen Block `num`  *  `size` Bytes. Jedes Element wird auf 0 initialisiert. Wenn `memblock` nicht `NULL` ist, wird ein Zeiger von einem vorherigen Aufruf an `calloc`, [malloc](../../c-runtime-library/reference/malloc.md) oder [realloc](../../c-runtime-library/reference/realloc.md) zurückgegeben.  
  
 Da der neue Block an einem neuen Speicherort liegen kann, kann nicht garantiert werden, dass der von `_recalloc` zurückgegebene Zeiger mit dem durch das `memblock`-Argument übergebenen Zeiger identisch ist.  
  
 `_recalloc` setzt `errno` auf `ENOMEM`, wenn eine Speicherbelegung fehlschlägt oder wenn der benötigte Speicherplatz größer als `_HEAP_MAXREQ` ist. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `recalloc` ruft `realloc` auf, um mithilfe der C++-Funktion [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) den neuen Handlermodus festzulegen. Der neue Handlermodus gibt an, ob bei einem Fehler die neue Handlerroutine von `realloc` aufgerufen werden soll, wie dies von [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md) festgelegt ist. Standardmäßig ruft `realloc` bei einem Speicherbelegungsfehler nicht die neue Handlerroutine auf. Sie können dieses Standardverhalten überschreiben, sodass, wenn `_recalloc` Speicher nicht belegen kann,`realloc` die neue Handlerroutine genauso aufruft wie der `new`-Operator, wenn dieser aus demselben Grund fehlschlägt. Um den Standardwert zu überschreiben, rufen Sie  
  
```  
_set_new_mode(1)  
```  
  
 rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit NEWMODE.OBJ her.  
  
 Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist `_recalloc` löst in [_recalloc_dbg](../../c-runtime-library/reference/recalloc-dbg.md). Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
 `_recalloc` ist als `__declspec(noalias)` und `__declspec(restrict)` gekennzeichnet, das bedeutet, dass die Funktion globale Variablen definitiv nicht ändert und dass der zurückgegebene Zeiger keinen Alias hat. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_recalloc`|\<stdlib.h> und \<malloc.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [_recalloc_dbg](../../c-runtime-library/reference/recalloc-dbg.md)   
 [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)   
 [_aligned_offset_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [Linkoptionen](../../c-runtime-library/link-options.md)