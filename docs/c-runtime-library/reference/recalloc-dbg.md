---
title: _recalloc_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _recalloc_dbg
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
- recalloc_dbg
- _recalloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- _recalloc_dbg function
- recalloc_dbg function
ms.assetid: 43c3e9b2-be6d-4508-9b0f-3220c8a47ca3
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 02ac41e22a5080576339b00e54f339bb878a794d
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="recallocdbg"></a>_recalloc_dbg
Ordnet ein Array neu zu und initialisiert seine Elemente auf 0 (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
void *_recalloc_dbg(   
   void *userData,  
   size_t num,  
   size_t size,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `userData`  
 Zeiger zum vorherigen belegten Speicherblock.  
  
 `num`  
 Angeforderte Anzahl von Speicherblöcken.  
  
 `size`  
 Angeforderte Größe eines Speicherblocks (Bytes).  
  
 `blockType`  
 Angeforderter Typ des Speicherblocks: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 Weitere Informationen zu den Zuordnungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details).  
  
 `filename`  
 Zeiger zum Namen der Quelldatei, der die Zuordnung angefordert hat, oder `NULL`.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Zuordnung angefordert wurde, oder `NULL`.  
  
 Die `filename`- und `linenumber`-Parameter sind nur verfügbar, wenn `_recalloc_dbg` explizit aufgerufen oder die [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)-Präprozessorkonstante definiert wurde.  
  
## <a name="return-value"></a>Rückgabewert  
 Bei erfolgreichem Abschluss gibt diese Funktion entweder einen Zeiger an den Benutzerteil des neu belegten Speicherblocks zurück, ruft die neue Handlerfunktion auf oder gibt NULL zurück. Eine vollständige Beschreibung des Rückgabeverhaltens finden Sie im folgenden Abschnitt "Hinweise". Weitere Informationen zur Verwendung der neuen Handlerfunktion finden Sie unter der [_recalloc](../../c-runtime-library/reference/recalloc.md)-Funktion.  
  
## <a name="remarks"></a>Hinweise  
 `_recalloc_dbg` ist eine Debugversion der [_recalloc](../../c-runtime-library/reference/recalloc.md)-Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder `_recalloc_dbg`-Aufruf zu einem `_recalloc`-Aufruf reduziert. Sowohl `_recalloc` als auch `_recalloc_dbg` belegen einen Speicherblock im Basisheap neu, jedoch verfügt `_recalloc_dbg` über mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzerteils des Blocks zum Prüfen auf Speicherverluste, einen Blocktypparameter zum Nachverfolgen bestimmter Belegungstypen und `filename`/`linenumber`-Informationen zum Ermitteln des Ursprungs von Belegungsanforderungen.  
  
 `_recalloc_dbg` ordnet den angegebenen Speicherblock mit etwas mehr Speicherplatz als die erforderliche Größe (`num` * `size`) neu zu, der größer oder kleiner als die Größe des ursprünglich zugeordneten Speicherblocks sein kann. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert. Der Benutzerteil des Blocks wird mit dem Wert 0xCD gefüllt, und jeder der Überschreibungspuffer wird mit 0xFD gefüllt.  
  
 `_recalloc_dbg` legt `errno` auf `ENOMEM` fest, wenn eine Speicherbelegung fehlschlägt. `EINVAL` wird zurückgegeben, wenn der benötigte Speicherplatz (einschließlich des bereits erwähnten Mehraufwands) `_HEAP_MAXREQ` überschreitet. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debugheapdetails](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_recalloc_dbg`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)