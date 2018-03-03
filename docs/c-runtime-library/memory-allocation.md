---
title: Speicherbelegung | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.memory
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.assetid: b4470556-a128-4782-9943-2ccf7a7d9979
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e419cbd30b523121ae1902b49a25d60c0b9d21eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="memory-allocation"></a>Speicherbelegung
Verwenden Sie diese Routinen zur Belegung, Freigabe und erneuten Belegung von Speicherplatz.  
  
### <a name="memory-allocation-routines"></a>Speicherbelegungsroutinen  
  
|-Routine zurückgegebener Wert|Mit|  
|-------------|---------|  
|[_alloca](../c-runtime-library/reference/alloca.md), [_malloca](../c-runtime-library/reference/malloca.md)|Belegen von Speicher im Stapel|  
|[calloc](../c-runtime-library/reference/calloc.md)|Belegen von Speicher für ein Array mit Initialisierung aller Bytes im belegten Block auf 0|  
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|Debugversion von `calloc`; nur in den Debugversionen der Laufzeitbibliotheken verfügbar|  
|[operator delete](../c-runtime-library/operator-delete-crt.md)|Freigeben eines belegten Blocks|  
|[operator delete&#91;&#93;](../c-runtime-library/delete-operator-crt.md)|Freigeben eines belegten Blocks|  
|[_expand](../c-runtime-library/reference/expand.md)|Erweitern oder Verkleinern eines Speicherblocks, ohne diesen zu bewegen|  
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|Debugversion von `_expand`; nur in den Debugversionen der Laufzeitbibliotheken verfügbar|  
|[free](../c-runtime-library/reference/free.md)|Freigeben eines belegten Blocks|  
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Debugversion von `free`; nur in den Debugversionen der Laufzeitbibliotheken verfügbar|  
|[_freea](../c-runtime-library/reference/freea.md)|Freigeben eines belegten Blocks aus dem Stapel|  
|[_get_heap_handle](../c-runtime-library/reference/get-heap-handle.md)|Abrufen des Win32 HANDLEs aus dem CRT-Heap.|  
|[_heapadd](../c-runtime-library/heapadd.md)|Hinzufügen von Speicher zum Heap.|  
|[_heapchk](../c-runtime-library/reference/heapchk.md)|Prüfen des Heaps auf Konsistenz|  
|[_heapmin](../c-runtime-library/reference/heapmin.md)|Freigeben von ungenutztem Speicher im Heap|  
|[_heapset](../c-runtime-library/heapset.md)|Füllen freier Heap-Einträge mit bestimmten Werten|  
|[_heapwalk](../c-runtime-library/reference/heapwalk.md)|Rückgabe von Informationen über jeden Eintrag im Heap|  
|[malloc](../c-runtime-library/reference/malloc.md)|Belegen von Speicherblöcken aus dem Heap|  
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|Debugversion von `malloc`; nur in den Debugversionen der Laufzeitbibliotheken verfügbar|  
|[_msize](../c-runtime-library/reference/msize.md)|Rückgabe der Größe des belegten Blocks|  
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|Debugversion von `_msize`; nur in den Debugversionen der Laufzeitbibliotheken verfügbar|  
|[new](../c-runtime-library/operator-new-crt.md)|Belegen von Speicherblöcken aus dem Heap|  
|[new&#91;&#93;](../c-runtime-library/new-operator-crt.md)|Belegen von Speicherblöcken aus dem Heap|  
|[_query_new_handler](../c-runtime-library/reference/query-new-handler.md)|Rückgabe der Adresse der aktuellen neuen Handlerroutine, wie in `_set_new_handler` festgelegt|  
|[_query_new_mode](../c-runtime-library/reference/query-new-mode.md)|Rückgabe einer Ganzzahl, die den von `_set_new_mode` für `malloc` festgelegten neuen Handlermodus anzeigt|  
|[realloc](../c-runtime-library/reference/realloc.md)|Erneute Belegung eines Blocks zur neuen Größe|  
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|Debugversion von `realloc`; nur in den Debugversionen der Laufzeitbibliotheken verfügbar|  
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Aktivieren des Fehlerbehandlungsmechanismus, wenn der Operator `new` zu einem Fehler führt (also kein Speicher belegt wird), sowie Aktivieren der Kompilierung von C++Standardbibliotheken|  
|[_set_new_mode](../c-runtime-library/reference/set-new-mode.md)|Festlegen eines neuen Handlermodus für `malloc`|  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)