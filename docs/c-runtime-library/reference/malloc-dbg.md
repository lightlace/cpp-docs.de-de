---
title: _malloc_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _malloc_dbg
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
- malloc_dbg
- _malloc_dbg
dev_langs: C++
helpviewer_keywords:
- malloc_dbg function
- memory allocation
- _malloc_dbg function
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fc67af9abb5602cca81eefa6aaeb131423057678
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mallocdbg"></a>_malloc_dbg
Belegt einen Speicherblock im Heap mit zusätzlichem Speicherplatz für einen Debugheader und Überschreibungspuffern (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
void *_malloc_dbg(  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `size`  
 Angeforderte Größe des Speicherblocks (Bytes).  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger zum Namen der Quelldatei, der die Belegung angefordert hat, oder NULL.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Belegung angefordert wurde, oder NULL.  
  
 Die `filename`- und `linenumber`-Parameter sind nur verfügbar, wenn `_malloc_dbg` explizit aufgerufen wurde oder die [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)-Präprozessorkonstante definiert wurde.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei erfolgreichem Abschluss gibt diese Funktion entweder einen Zeiger an den Benutzerteil des belegten Speicherblocks zurück, ruft die neue Handlerfunktion auf oder gibt NULL zurück. Eine vollständige Beschreibung des Rückgabeverhaltens finden Sie im folgenden Abschnitt "Hinweise". Weitere Informationen zur Verwendung der neuen Handlerfunktion finden Sie unter der [malloc](../../c-runtime-library/reference/malloc.md)-Funktion.  
  
## <a name="remarks"></a>Hinweise  
 `_malloc_dbg` ist eine Debugversion der [malloc](../../c-runtime-library/reference/malloc.md)-Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder Aufruf von `_malloc_dbg` zu einem Aufruf von `malloc` reduziert. Sowohl `malloc` als auch `_malloc_dbg` belegen einen Speicherblock im Basisheap, jedoch bietet `_malloc_dbg` mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzerteils des Blocks zum Prüfen auf Speicherverluste, einen Blocktypparameter zum Nachverfolgen von bestimmten Belegungstypen und `filename`/`linenumber`-Informationen zum Ermitteln des Ursprungs von Belegungsanforderungen.  
  
 `_malloc_dbg` belegt den Speicherblock mit etwas mehr Speicherplatz als der angeforderten `size`. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Wenn der Block belegt wurde, wird der Benutzerteil des Blocks mit dem Wert "0xCD" gefüllt, und jeder der Überschreibungspuffer wird mit "0xFD" gefüllt.  
  
 `_malloc_dbg` legt `errno` auf `ENOMEM` fest, wenn eine Speicherbelegung fehlschlägt oder der benötigte Speicherplatz (einschließlich des bereits erwähnten Mehraufwands) `_HEAP_MAXREQ` überschreitet. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Informationen über die Belegung, Initialisierung und Verwaltung der Speicherblöcke in der Debugversion des Basisheaps finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_malloc_dbg`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung von `_malloc_dbg` finden Sie unter [crt_dbg1](http://msdn.microsoft.com/en-us/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_calloc_dbg](../../c-runtime-library/reference/calloc-dbg.md)   
 [_calloc_dbg](../../c-runtime-library/reference/calloc-dbg.md)