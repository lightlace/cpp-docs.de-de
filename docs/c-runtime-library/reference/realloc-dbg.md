---
title: "_realloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_realloc_dbg"
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
  - "_realloc_dbg"
  - "realloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Neuzuordnen von Arbeitsspeicherblöcken"
  - "realloc_dbg-Funktion"
  - "Arbeitsspeicherblöcke, Neuzuordnen"
  - "Arbeitsspeicher, Neuzuordnen"
  - "_realloc_dbg-Funktion"
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _realloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Belegt einen angegebenen Speicherblock im Heap durch Verschieben und\/oder Ändern der Größe des Blocks erneut \(nur Debugversion\).  
  
## Syntax  
  
```  
void *_realloc_dbg(  
   void *userData,  
   size_t newSize,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### Parameter  
 `userData`  
 Zeiger zum vorherigen belegten Speicherblock.  
  
 `newSize`  
 Angeforderte Größe für den neu belegten Block \(Bytes\).  
  
 `blockType`  
 Angeforderter Typ für den neu zugeordneten Block: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger zum Namen der Quelldatei, der den `realloc`\-Vorgang angefordert hat, oder NULL.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der der `realloc`\-Vorgang angefordert wurde, oder NULL.  
  
 Die `filename`\- und `linenumber`\-Parameter sind nur verfügbar, wenn `_realloc_dbg` explizit aufgerufen wurde oder die [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)\-Präprozessorkonstante definiert wurde.  
  
## Rückgabewert  
 Bei erfolgreichem Abschluss gibt diese Funktion entweder einen Zeiger an den Benutzerteil des neu belegten Speicherblocks zurück, ruft die neue Handlerfunktion auf oder gibt NULL zurück.  Eine vollständige Beschreibung des Rückgabeverhaltens finden Sie im folgenden Abschnitt "Hinweise".  Weitere Informationen zur Verwendung der neuen Handlerfunktion finden Sie unter der [realloc](../../c-runtime-library/reference/realloc.md)\-Funktion.  
  
## Hinweise  
 `_realloc_dbg` ist eine Debugversion der [realloc](../../c-runtime-library/reference/realloc.md)\-Funktion.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder Aufruf von `_realloc_dbg` zu einem Aufruf von `realloc` reduziert.  Sowohl `realloc` als auch `_realloc_dbg` belegen einen Speicherblock im Basisheap neu, jedoch verfügt `_realloc_dbg` über mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzerteils des Blocks zum Prüfen auf Speicherverluste, einen Blocktypparameter zum Nachverfolgen von bestimmten Belegungstypen und `filename`\/`linenumber`\-Informationen zum Ermitteln des Ursprungs von Belegungsanforderungen.  
  
 `_realloc_dbg` belegt den angegebenen Speicherblock neu mit etwas mehr Speicherplatz als der angeforderten `newSize`.  `newSize` kann größer oder kleiner sein als die Größe des ursprünglich belegten Speicherblocks.  Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen.  Durch die Neubelegung wird der ursprüngliche Speicherblock möglicherweise an einen anderen Speicherort im Heap verschoben und auch die Größe des Speicherblocks geändert.  Wenn der Speicherblock verschoben wird, wird der Inhalt des ursprünglichen Blocks überschrieben.  
  
 `_realloc_dbg` legt `errno` auf `ENOMEM` fest, wenn eine Speicherbelegung fehlschlägt oder der benötigte Speicherplatz \(einschließlich des bereits erwähnten Mehraufwands\) `_HEAP_MAXREQ` überschreitet.  Informationen zu diesem und anderen Fehlercodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  Weitere Informationen zu den Zuordnungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapreservierungsfunktionen](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_realloc_dbg`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Ein Beispiel finden Sie im Thema [\_msize\_dbg](../../c-runtime-library/reference/msize-dbg.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)