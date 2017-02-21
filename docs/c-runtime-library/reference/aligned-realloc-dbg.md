---
title: "_aligned_realloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_realloc_dbg"
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
  - "aligned_realloc_dbg"
  - "_aligned_realloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_realloc_dbg-Funktion"
  - "aligned_realloc_dbg-Funktion"
ms.assetid: 8aede920-991e-44cd-867f-83dc2165db47
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _aligned_realloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) belegt ist \(nur in der Debugversion\).  
  
## Syntax  
  
```  
void * _aligned_realloc_dbg(    void *memblock,     size_t size,     size_t alignment,    const char *filename,    int linenumber  );  
```  
  
#### Parameter  
 \[in\] `memblock`  
 Der Zeiger auf den aktuellen Speicherblock.  
  
 \[in\] `size`  
 Die Größe der angeforderten Speicherbelegung.  
  
 \[in\] `alignment`  
 Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.  
  
 \[in\] `filename`  
 Zeiger zum Namen der Quelldatei, der den `realloc`\-Vorgang angefordert hat, oder NULL.  
  
 \[in\] `linenumber`  
 Zeilennummer in der Quelldatei, in der der `realloc`\-Vorgang angefordert wurde, oder NULL.  
  
## Rückgabewert  
 `_aligned_realloc_dbg` gibt einen leeren Zeiger auf den neu belegten \(und möglicherweise verschobenen\) Speicherblock zurück.  Der Rückgabewert ist `NULL`, wenn die Größe 0 ist und das Pufferargument nicht `NULL` ist oder wenn nicht genügend Speicherplatz vorhanden ist, um den Block auf die vorgegebene Größe auszudehnen.  Im ersten Fall wird der ursprüngliche Block freigegeben.  Im zweiten Fall wird der ursprüngliche Block nicht geändert.  Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist.  Um einen Zeiger auf einen anderen Typ als den leeren zurückzugeben, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
 Es ist ein Fehler, wenn ein Speicher neu belegt und die Ausrichtung eines Blocks geändert wird.  
  
## Hinweise  
 `_aligned_realloc_dbg` ist eine Debugversion der [\_aligned\_realloc](../../c-runtime-library/reference/aligned-realloc.md)\-Funktion.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder Aufruf von `_aligned_realloc_dbg` zu einem Aufruf von `aligned_realloc` reduziert.  Sowohl `aligned_realloc` als auch `_aligned_realloc_dbg` belegen einen Speicherblock im Basisheap neu, jedoch verfügt `_aligned_realloc_dbg` über mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzerteils des Blocks zum Prüfen auf Speicherverluste, einen Blocktypparameter zum Nachverfolgen bestimmter Belegungstypen und `filename`\/`linenumber`\-Informationen zum Ermitteln des Ursprungs von Belegungsanforderungen.  
  
 `_aligned_realloc_dbg` belegt den angegebenen Speicherblock neu mit etwas mehr Speicherplatz als der angeforderten `newSize`.  `newSize` kann größer oder kleiner sein als die Größe des ursprünglich belegten Speicherblocks.  Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen.  Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert.  Wenn der Speicherblock verschoben wird, wird der Inhalt des ursprünglichen Blocks überschrieben.  
  
 `_aligned_realloc_dbg` legt `errno` auf `ENOMEM` fest, wenn eine Speicherbelegung fehlschlägt oder der benötigte Speicherplatz \(einschließlich des bereits erwähnten Mehraufwands\) `_HEAP_MAXREQ` überschreitet.  Informationen zu diesem und anderen Fehlercodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Darüber hinaus überprüft `_aligned_realloc_dbg` auch die eigenen Parameter.  Wenn `alignment` keine Potenz von 2 ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und stellt `errno` auf `NULL` ein.  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  Weitere Informationen zu den Zuordnungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapreservierungsfunktionen](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_aligned_realloc_dbg`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)