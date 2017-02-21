---
title: "_aligned_free_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_free_dbg"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_aligned_free_dbg"
  - "aligned_free_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_free_dbg-Funktion"
  - "aligned_free_dbg-Funktion"
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _aligned_free_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Speicherblock frei, der mit [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist \(nur in der Debugversion\).  
  
## Syntax  
  
```  
void _aligned_free_dbg(    void *memblock );  
```  
  
#### Parameter  
 `memblock`  
 Ein Zeiger auf den Speicherblock, der an die Funktion `_aligned_malloc` oder `_aligned_offset_malloc` zurückgegeben wurde.  
  
## Hinweise  
 Die Funktion `_aligned_free_dbg`  ist eine Debugversion der Funktion [\_aligned\_free](../../c-runtime-library/reference/aligned-free.md).  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder Aufruf von `_aligned_free_dbg` zu einem Aufruf von `aligned_free` reduziert.  Sowohl\_`aligned_free` als auch `_aligned_free_dbg` geben einen Speicherblock im Basisheap frei, jedoch hat `_aligned_free_dbg`  eine Debugfunktion: die Möglichkeit, freigegebene Blöcke in der verknüpften Liste des Heaps beizubehalten, um Speichermangel zu simulieren.  
  
 `_aligned_free_dbg` führt eine Gültigkeitsüberprüfung für alle angegebenen Dateien und Blockspeicherorte aus, bevor eine Freigabe erfolgt.  Die Anwendung stellt diese Informationen wahrscheinlich nicht bereit.  Wenn ein Speicherblock freigegeben wird, überprüft der Debugheapmanager automatisch die Pufferintegrität auf beiden Seiten des Benutzerteils und erstellt einen Fehlerbericht, falls über den Puffer hinaus geschrieben wurde.  Wenn das Bitfeld `_CRTDBG_DELAY_FREE_MEM_DF` des [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)\-Flags festgelegt ist, wird der freigegebene Block mit dem Wert "0xDD" gefüllt. Außerdem wird der `_FREE_BLOCK`\-Blocktyp zugewiesen und in der verknüpften Liste des Heaps im Speicherblock beibehalten.  
  
 Wenn bei der Freigabe des Speichers ein Fehler auftritt, wird `errno` mit Informationen des Betriebssystems über die Art des Fehlers angegeben.  Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  Weitere Informationen zu den Zuordnungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapreservierungsfunktionen](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_aligned_free_dbg`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)