---
title: _aligned_realloc_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _aligned_realloc_dbg
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
- aligned_realloc_dbg
- _aligned_realloc_dbg
dev_langs: C++
helpviewer_keywords:
- _aligned_realloc_dbg function
- aligned_realloc_dbg function
ms.assetid: 8aede920-991e-44cd-867f-83dc2165db47
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3145a78a145bed52fc30e64dbcf56210341d52cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="alignedreallocdbg"></a>_aligned_realloc_dbg
Ändert die Größe eines Speicherblocks, der mit [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist (nur in der Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
void * _aligned_realloc_dbg(  
   void *memblock,   
   size_t size,   
   size_t alignment,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `memblock`  
 Der Zeiger auf den aktuellen Speicherblock.  
  
 [in] `size`  
 Die Größe der angeforderten Speicherbelegung.  
  
 [in] `alignment`  
 Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.  
  
 [in] `filename`  
 Zeiger zum Namen der Quelldatei, der den `realloc`-Vorgang angefordert hat, oder NULL.  
  
 [in] `linenumber`  
 Zeilennummer in der Quelldatei, in der der `realloc`-Vorgang angefordert wurde, oder NULL.  
  
## <a name="return-value"></a>Rückgabewert  
 `_aligned_realloc_dbg` gibt einen leeren Zeiger auf den neu belegten (und möglicherweise verschobenen) Speicherblock zurück. Der Rückgabewert ist `NULL`, wenn die Größe 0 ist und das Pufferargument nicht `NULL` ist oder wenn nicht genügend Speicherplatz vorhanden ist, um den Block auf die vorgegebene Größe auszudehnen. Im ersten Fall wird der ursprüngliche Block freigegeben. Im zweiten Fall wird der ursprüngliche Block nicht geändert. Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einen anderen Typ als den leeren zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
 Es ist ein Fehler, wenn ein Speicher neu belegt und die Ausrichtung eines Blocks geändert wird.  
  
## <a name="remarks"></a>Hinweise  
 `_aligned_realloc_dbg` ist eine Debugversion der [_aligned_realloc](../../c-runtime-library/reference/aligned-realloc.md)-Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder `_aligned_realloc_dbg`-Aufruf zu einem `_aligned_realloc`-Aufruf reduziert. Sowohl `_aligned_realloc` als auch `_aligned_realloc_dbg` belegen einen Speicherblock im Basisheap neu, jedoch verfügt `_aligned_realloc_dbg` über mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzerteils des Blocks zum Prüfen auf Speicherverluste, einen Blocktypparameter zum Nachverfolgen bestimmter Belegungstypen und `filename`/`linenumber`-Informationen zum Ermitteln des Ursprungs von Belegungsanforderungen.  
  
 `_aligned_realloc_dbg` belegt den angegebenen Speicherblock neu mit etwas mehr Speicherplatz als der angeforderten `newSize`. `newSize` kann größer oder kleiner sein als die Größe des ursprünglich belegten Speicherblocks. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert. Wenn der Speicherblock verschoben wird, wird der Inhalt des ursprünglichen Blocks überschrieben.  
  
 `_aligned_realloc_dbg` legt `errno` auf `ENOMEM` fest, wenn eine Speicherbelegung fehlschlägt oder der benötigte Speicherplatz (einschließlich des bereits erwähnten Mehraufwands) `_HEAP_MAXREQ` überschreitet. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Darüber hinaus überprüft `_aligned_realloc_dbg` auch die eigenen Parameter. Wenn `alignment` keine Potenz von 2, ruft diese Funktion den Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und stellt `errno` auf `EINVAL` ein.  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details (CRT Debug Heap-Details)](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_aligned_realloc_dbg`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)