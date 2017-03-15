---
title: _recalloc_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: de222892bc12668359b4e52e0362ca9437ba2d0b
ms.lasthandoff: 02/24/2017

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
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)
