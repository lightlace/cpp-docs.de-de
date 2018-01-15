---
title: _free_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _free_dbg
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
- _free_dbg
- free_dbg
dev_langs: C++
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fccae4629bc4c1c9b6af71f254c28311210ec0e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="freedbg"></a>_free_dbg
Gibt einen Speicherblock im Heap frei (nur Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
void _free_dbg(   
   void *userData,  
   int blockType   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `userData`  
 Zeiger zum belegten Speicherblock, der freigegeben werden soll.  
  
 `blockType`  
 Typ des belegten, freizugebenden Speicherblocks: `_CLIENT_BLOCK`, `_NORMAL_BLOCK` oder `_IGNORE_BLOCK`.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_free_dbg` ist eine Debugversion der Funktion [free](../../c-runtime-library/reference/free.md). Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder `_free_dbg`-Aufruf zu einem `free`-Aufruf reduziert. `free` und `_free_dbg` geben einen Speicherblock im Basisheap frei, jedoch hat `_free_dbg` zwei Debugfunktionen: die Möglichkeit, freigegebene Blöcke in der verknüpften Liste des Heaps beizubehalten, um Speichermangel zu simulieren, und einen Blocktypparameter zum Freigeben bestimmter Belegungstypen.  
  
 `_free_dbg` führt eine Gültigkeitsüberprüfung für alle angegebenen Dateien und Blockspeicherorte aus, bevor eine Freigabe erfolgt. Die Anwendung stellt diese Informationen wahrscheinlich nicht bereit. Wenn ein Speicherblock freigegeben wird, überprüft der Debugheapmanager automatisch die Pufferintegrität auf beiden Seiten des Benutzerteils und erstellt einen Fehlerbericht, falls über den Puffer hinaus geschrieben wurde. Wenn das Bitfeld `_CRTDBG_DELAY_FREE_MEM_DF` des [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)-Flags festgelegt ist, wird der freigegebene Block mit dem Wert „0xDD“ gefüllt. Außerdem wird dem Block der `_FREE_BLOCK`-Blocktyp zugewiesen und in der verknüpften Liste des Heaps im Speicherblock beibehalten.  
  
 Wenn bei der Freigabe des Speichers ein Fehler auftritt, wird `errno` mit Informationen des Betriebssystems über die Art des Fehlers angegeben. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap-Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_free_dbg`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung von `_free_dbg` finden Sie unter [crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)