---
title: Speicherbelegung | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ae7869beb76e5e1f0514c3459beab65530e31cba
ms.lasthandoff: 02/24/2017

---
# <a name="memory-allocation"></a>Speicherbelegung
Verwenden Sie diese Routinen zur Belegung, Freigabe und erneuten Belegung von Speicherplatz.  
  
### <a name="memory-allocation-routines"></a>Speicherbelegungsroutinen  
  
|Routine|Verwendung|.NET Framework-Entsprechung|  
|-------------|---------|-------------------------------|  
|[_alloca](../c-runtime-library/reference/alloca.md), [_malloca](../c-runtime-library/reference/malloca.md)|Belegen von Speicher im Stapel|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[calloc](../c-runtime-library/reference/calloc.md)|Belegen von Speicher für ein Array mit Initialisierung aller Bytes im belegten Block auf 0|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples (Beispiele für Plattformaufrufe)](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|Debugversion von `calloc`; nur in den Debugversionen der Laufzeitbibliotheken verfügbar|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[operator delete](../c-runtime-library/operator-delete-crt.md)|Freigeben eines belegten Blocks|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[operator delete&#91;&#93;](../c-runtime-library/delete-operator-crt.md)|Freigeben eines belegten Blocks|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_expand](../c-runtime-library/reference/expand.md)|Erweitern oder Verkleinern eines Speicherblocks, ohne diesen zu bewegen|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples (Beispiele für Plattformaufrufe)](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|Debugversion von `_expand`; nur in den Debugversionen der Laufzeitbibliotheken verfügbar|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[free](../c-runtime-library/reference/free.md)|Freigeben eines belegten Blocks|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples (Beispiele für Plattformaufrufe)](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Debugversion von `free`; nur in den Debugversionen der Laufzeitbibliotheken verfügbar|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_freea](../c-runtime-library/reference/freea.md)|Freigeben eines belegten Blocks aus dem Stapel|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_get_heap_handle](../c-runtime-library/reference/get-heap-handle.md)|Abrufen des Win32 HANDLEs aus dem CRT-Heap.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_heapadd](../c-runtime-library/heapadd.md)|Hinzufügen von Speicher zum Heap.|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_heapchk](../c-runtime-library/reference/heapchk.md)|Prüfen des Heaps auf Konsistenz|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_heapmin](../c-runtime-library/reference/heapmin.md)|Freigeben von ungenutztem Speicher im Heap|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_heapset](../c-runtime-library/heapset.md)|Füllen freier Heap-Einträge mit bestimmten Werten|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_heapwalk](../c-runtime-library/reference/heapwalk.md)|Rückgabe von Informationen über jeden Eintrag im Heap|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[malloc](../c-runtime-library/reference/malloc.md)|Belegen von Speicherblöcken aus dem Heap|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples (Beispiele für Plattformaufrufe)](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|Debugversion von `malloc`; nur in den Debugversionen der Laufzeitbibliotheken verfügbar|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_msize](../c-runtime-library/reference/msize.md)|Rückgabe der Größe des belegten Blocks|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples (Beispiele für Plattformaufrufe)](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|Debugversion von `_msize`; nur in den Debugversionen der Laufzeitbibliotheken verfügbar|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[new](../c-runtime-library/operator-new-crt.md)|Belegen von Speicherblöcken aus dem Heap|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[new&#91;&#93;](../c-runtime-library/new-operator-crt.md)|Belegen von Speicherblöcken aus dem Heap|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_query_new_handler](../c-runtime-library/reference/query-new-handler.md)|Rückgabe der Adresse der aktuellen neuen Handlerroutine, wie in `_set_new_handler` festgelegt|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_query_new_mode](../c-runtime-library/reference/query-new-mode.md)|Rückgabe einer Ganzzahl, die den von `_set_new_mode` für `malloc` festgelegten neuen Handlermodus anzeigt|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[realloc](../c-runtime-library/reference/realloc.md)|Erneute Belegung eines Blocks zur neuen Größe|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples (Beispiele für Plattformaufrufe)](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|Debugversion von `realloc`; nur in den Debugversionen der Laufzeitbibliotheken verfügbar|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Aktivieren des Fehlerbehandlungsmechanismus, wenn der Operator `new` zu einem Fehler führt (also kein Speicher belegt wird), sowie Aktivieren der Kompilierung von C++Standardbibliotheken|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_set_new_mode](../c-runtime-library/reference/set-new-mode.md)|Festlegen eines neuen Handlermodus für `malloc`|Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
