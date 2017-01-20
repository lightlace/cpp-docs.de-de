---
title: "_free_dbg"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_free_dbg"
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
  - "_free_dbg"
  - "free_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Speicherblöcke, Freigeben"
  - "Freigeben von Arbeitsspeicher"
  - "_free_dbg-Funktion"
  - "free_dbg-Funktion"
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# _free_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Speicherblock im Heap frei \(nur Debugversion\).  
  
## Syntax  
  
```  
void _free_dbg(   
   void *userData,  
   int blockType   
);  
```  
  
#### Parameter  
 `userData`  
 Zeiger zum belegten Speicherblock, der freigegeben werden soll.  
  
 `blockType`  
 Typ des belegten, freizugebenden Speicherblocks: `_CLIENT_BLOCK`, `_NORMAL_BLOCK` oder `_IGNORE_BLOCK`.  
  
## Hinweise  
 Die Funktion `_free_dbg` ist eine Debugversion der [free](../../c-runtime-library/reference/free.md)\-Funktion.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder Aufruf von `_free_dbg` zu einem Aufruf von `free` reduziert.  `free` und `_free_dbg` geben einen Speicherblock im Basisheap frei, jedoch hat `_free_dbg` zwei Debugfunktionen: die Möglichkeit, freigegebene Blöcke in der verknüpften Liste des Heaps beizubehalten, um Speichermangel zu simulieren, und einen Blocktypparameter zum Freigeben bestimmter Belegungstypen.  
  
 `_free_dbg` führt eine Gültigkeitsüberprüfung für alle angegebenen Dateien und Blockspeicherorte aus, bevor eine Freigabe erfolgt.  Die Anwendung stellt diese Informationen wahrscheinlich nicht bereit.  Wenn ein Speicherblock freigegeben wird, überprüft der Debugheapmanager automatisch die Pufferintegrität auf beiden Seiten des Benutzerteils und erstellt einen Fehlerbericht, falls über den Puffer hinaus geschrieben wurde.  Wenn das Bitfeld `_CRTDBG_DELAY_FREE_MEM_DF` des [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)\-Flags festgelegt ist, wird der freigegebene Block mit dem Wert "0xDD" gefüllt. Außerdem wird der `_FREE_BLOCK`\-Blocktyp zugewiesen und in der verknüpften Liste des Heaps im Speicherblock beibehalten.  
  
 Wenn bei der Freigabe des Speichers ein Fehler auftritt, wird `errno` mit Informationen des Betriebssystems über die Art des Fehlers angegeben.  Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  Weitere Informationen zu den Zuordnungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapreservierungsfunktionen](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_free_dbg`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Ein Beispiel für die Verwendung von `_free_dbg` finden Sie unter [crt\_dbg2](assetId:///21e1346a-6a17-4f57-b275-c76813089167).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)