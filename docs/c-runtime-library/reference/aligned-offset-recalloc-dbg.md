---
title: _aligned_offset_recalloc_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_offset_recalloc_dbg
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
apitype: DLLExport
f1_keywords:
- aligned_offset_recalloc_dbg
- _aligned_offset_recalloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_recalloc_dbg function
- _aligned_offset_recalloc_dbg function
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
caps.latest.revision: 9
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
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 04a060699b23bfc5dfaba5da0d41a522455eb03a
ms.lasthandoff: 02/24/2017

---
# <a name="alignedoffsetrecallocdbg"></a>_aligned_offset_recalloc_dbg
Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist und den Speicher auf 0 initialisiert (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
void * _aligned_offset_recalloc_dbg(  
   void *memblock,   
   size_t num,   
   size_t size,   
   size_t alignment,  
   size_t offset,  
   const char *filename,  
   int linenumber  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `memblock`  
 Der Zeiger auf den aktuellen Speicherblock.  
  
 [in] `num`  
 Anzahl der Elemente.  
  
 [in] `size`  
 Länge jedes Elements in Bytes.  
  
 [in] `alignment`  
 Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.  
  
 [in] `offset`  
 Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.  
  
 [in] `filename`  
 Zeiger zum Namen der Quelldatei, der den `realloc`-Vorgang angefordert hat, oder NULL.  
  
 [in] `linenumber`  
 Zeilennummer in der Quelldatei, in der der `realloc`-Vorgang angefordert wurde, oder NULL.  
  
## <a name="return-value"></a>Rückgabewert  
 `_aligned_offset_recalloc_dbg` gibt einen leeren Zeiger auf den neu belegten (und möglicherweise verschobenen) Speicherblock zurück. Der Rückgabewert ist `NULL`, wenn die Größe&0; ist und das Pufferargument nicht `NULL` ist oder wenn nicht genügend Speicherplatz vorhanden ist, um den Block auf die vorgegebene Größe auszudehnen. Im ersten Fall wird der ursprüngliche Block freigegeben. Im zweiten Fall wird der ursprüngliche Block nicht geändert. Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einen anderen Typ als den leeren zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
## <a name="remarks"></a>Hinweise  
 `_aligned_offset_realloc_dbg` ist eine Debugversion der [_aligned_offset_recalloc](../../c-runtime-library/reference/aligned-offset-recalloc.md)-Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder Aufruf von `_aligned_offset_recalloc_dbg` zu einem Aufruf von `aligned_offset_recalloc` reduziert. Sowohl \_`aligned_offset_recalloc` als auch `_aligned_offset_recalloc_dbg` belegen einen Speicherblock im Basisheap neu, jedoch verfügt `_aligned_offset_recalloc_dbg` über mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzerteils des Blocks zum Prüfen auf Speicherverluste, einen Blocktypparameter zum Nachverfolgen bestimmter Belegungstypen und `filename`/`linenumber`-Informationen zum Ermitteln des Ursprungs von Belegungsanforderungen.  
  
 `_aligned_offset_realloc_dbg` belegt den angegebenen Speicherblock neu mit etwas mehr Speicherplatz als der angeforderten `newSize`. `newSize` kann größer oder kleiner sein als die Größe des ursprünglich belegten Speicherblocks. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert. Wenn der Speicherblock verschoben wird, wird der Inhalt des ursprünglichen Blocks überschrieben.  
  
 Diese Funktion legt `errno` auf `ENOMEM` fest, wenn die Speicherbelegung fehlgeschlagen ist oder die angeforderte Größe(`num` * `size`) größer als `_HEAP_MAXREQ` war. Weitere Informationen zu `errno` finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Darüber hinaus überprüft `_aligned_offset_recalloc_dbg` auch die eigenen Parameter. Wenn `alignment` keine Potenz von 2 ist oder `offset` größer als oder gleich der angeforderten Größe und ungleich 0 ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und stellt `errno` auf `EINVAL` ein.  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details (CRT Debug Heap-Details)](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_aligned_offset_recalloc_dbg`|\<malloc.h>|  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Datenausrichtung](../../c-runtime-library/data-alignment.md)
