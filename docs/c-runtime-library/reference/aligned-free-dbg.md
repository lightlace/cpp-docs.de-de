---
title: _aligned_free_dbg | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_free_dbg
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
- _aligned_free_dbg
- aligned_free_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
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
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 40a42d694d6f0101573cb9b29e5a7571c4863bb0
ms.lasthandoff: 02/24/2017

---
# <a name="alignedfreedbg"></a>_aligned_free_dbg
Gibt einen Speicherblock frei, der mit [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) oder [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist (nur in der Debugversion).  
  
## <a name="syntax"></a>Syntax  
  
```  
void _aligned_free_dbg(  
   void *memblock  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `memblock`  
 Ein Zeiger auf den Speicherblock, der an die Funktion `_aligned_malloc` oder `_aligned_offset_malloc` zurückgegeben wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_aligned_free_dbg`ist eine Debugversion der [_aligned_free](../../c-runtime-library/reference/aligned-free.md)-Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder Aufruf von `_aligned_free_dbg` zu einem Aufruf von _`aligned_free` reduziert. Sowohl \_`aligned_free` als auch `_aligned_free_dbg` geben einen Speicherblock im Basisheap frei, jedoch hat `_aligned_free_dbg` eine Debugfunktion: die Möglichkeit, freigegebene Blöcke in der verknüpften Liste des Heaps beizubehalten, um Speichermangel zu simulieren.  
  
 `_aligned_free_dbg` führt eine Gültigkeitsüberprüfung für alle angegebenen Dateien und Blockspeicherorte aus, bevor eine Freigabe erfolgt. Die Anwendung stellt diese Informationen wahrscheinlich nicht bereit. Wenn ein Speicherblock freigegeben wird, überprüft der Debugheapmanager automatisch die Pufferintegrität auf beiden Seiten des Benutzerteils und erstellt einen Fehlerbericht, falls über den Puffer hinaus geschrieben wurde. Wenn das Bitfeld `_CRTDBG_DELAY_FREE_MEM_DF` des [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)-Flags festgelegt ist, wird der freigegebene Block mit dem Wert „0xDD“ gefüllt. Außerdem wird dem Block der `_FREE_BLOCK`-Blocktyp zugewiesen und in der verknüpften Liste des Heaps im Speicherblock beibehalten.  
  
 Wenn bei der Freigabe des Speichers ein Fehler auftritt, wird `errno` mit Informationen des Betriebssystems über die Art des Fehlers angegeben. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap-Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und ihrer Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapbelegungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_aligned_free_dbg`|\<crtdbg.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Nicht zutreffend. Mit `PInvoke`rufen Sie die Standard-C-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)
