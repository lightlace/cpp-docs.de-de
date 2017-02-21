---
title: "_aligned_recalloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_recalloc_dbg"
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
  - "_aligned_recalloc_dbg"
  - "aligned_recalloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_recalloc_dbg-Funktion"
  - "aligned_recalloc_dbg-Funktion"
ms.assetid: 55c3c27e-561c-4d6b-9bf9-1e34cc556e4b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# _aligned_recalloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde und initialisiert den Speicher auf 0 \(nur Debugversion\).  
  
## Syntax  
  
```  
void * _aligned_recalloc_dbg(    void * memblock,     size_t num,    size_t size,     size_t alignment,    const char *filename,    int linenumber );  
```  
  
#### Parameter  
 \[in\] `memblock`  
 Der aktuelle Speicherblockzeiger.  
  
 \[in\] `num`  
 Die Anzahl der Elemente.  
  
 \[in\] `size`  
 Die Größe jedes Elements in Byte.  
  
 \[in\] `alignment`  
 Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.  
  
 \[in\] `filename`  
 Zeiger zum Namen der Quelldatei, der die Zuordnung angefordert hat, oder `NULL`.  
  
 \[in\] `linenumber`  
 Zeilennummer in der Quelldatei, in der die Zuordnung angefordert wurde, oder `NULL`.  
  
## Rückgabewert  
 `_aligned_recalloc_dbg` gibt einen void\-Zeiger zum neu zugeordneten \(und möglicherweise verschobenen\) Speicherblock zurück.  Der Rückgabewert ist `NULL`, wenn die Größe Null und das Pufferargument nicht `NULL` ist oder wenn nicht genügend Speicher verfügbar ist, um den Block auf die angegebene Größe zu erweitern.  Im ersten Fall wird der ursprüngliche Block freigegeben.  Im zweiten Fall bleibt der ursprüngliche Block unverändert.  Der Rückgabewert zeigt auf einen Speicherplatz, der garantiert zum Speichern jedes Objekttyps geeignet ist.  Um einen Zeiger auf einen anderen Typ als void abzurufen, verwenden Sie eine Typumwandlung für den Rückgabewert.  
  
 Es ist ein Fehler, Speicher erneut zuzuordnen und die Ausrichtung eines Blocks zu ändern.  
  
## Hinweise  
 `_aligned_recalloc_dbg` ist eine Debugversion der [\_aligned\_recalloc](../../c-runtime-library/reference/aligned-recalloc.md)\-Funktion.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder Aufruf von `_aligned_recalloc_dbg` zu einem Aufruf von `_aligned_recalloc` reduziert.  Sowohl `_aligned_recalloc` als auch `_aligned_recalloc_dbg` belegen einen Speicherblock im Basisheap neu, jedoch verfügt `_aligned_recalloc_dbg` über mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzerteils des Blocks zum Prüfen auf Speicherverluste, einen Blocktypparameter zum Nachverfolgen von bestimmten Belegungstypen und `filename`\/`linenumber`\-Informationen zum Ermitteln des Ursprungs von Belegungsanforderungen.  
  
 `_aligned_recalloc_dbg` ordnet den angegebenen Speicherblock mit etwas mehr Speicherplatz als die erforderliche Größe \(`num` \* `size`\) neu zu, die größer oder kleiner als die Größe des ursprünglich zugeordneten Speicherblocks sein kann.  Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen.  Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert.  Der Benutzerteil des Blocks wird mit dem Wert 0xCD gefüllt, und die Überschreibungspuffer werden mit 0xFD gefüllt.  
  
 `_aligned_recalloc_dbg` legt `errno` auf `ENOMEM` fest, wenn eine Speicherbelegung fehlschlägt. `EINVAL` wird zurückgegeben, wenn der benötigte Speicherplatz \(einschließlich des bereits erwähnten Mehraufwands\) `_HEAP_MAXREQ` überschreitet.  Informationen zu diesem und anderen Fehlercodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Darüber hinaus überprüft `_aligned_recalloc_dbg` auch die eigenen Parameter.  Wenn `alignment` keine Potenz von 2 ist, ruft diese Funktion den Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und stellt `errno` auf `NULL` ein.  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  Informationen zu den Zuordnungsblocktypen und deren Verwendung finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapreservierungsfunktionen](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_aligned_recalloc_dbg`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)