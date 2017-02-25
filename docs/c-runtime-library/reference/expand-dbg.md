---
title: "_expand_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_expand_dbg"
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
  - "expand_dbg"
  - "_expand_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Speicherblöcke, Ändern der Größe"
  - "expand_dbg-Funktion"
  - "_expand_dbg-Funktion"
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _expand_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändert die Größe eines angegebenen Speicherblocks im Heap durch Erweitern oder Verkürzen des Blocks \(nur Debugversion\).  
  
## Syntax  
  
```  
void *_expand_dbg(   
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
 Angeforderte neue Größe des Blocks \(in Bytes\).  
  
 `blockType`  
 Angeforderter Typ für vergrößerten\/verkleinerten Block: `_CLIENT_BLOCK` oder `_NORMAL_BLOCK`.  
  
 `filename`  
 Zeiger zum Namen der Quelldatei, der die Erweiterung angefordert hat, oder `NULL`.  
  
 `linenumber`  
 Zeilennummer in der Quelldatei, in der die Erweiterung angefordert wurde, oder `NULL`.  
  
 Die `filename`\- und `linenumber`\-Parameter sind nur verfügbar, wenn `_expand_dbg` explizit aufgerufen wurde oder die [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)\-Präprozessorkonstante definiert wurde.  
  
## Rückgabewert  
 Bei erfolgreichem Abschluss gibt `_expand_dbg` einen Zeiger zum vergrößerten\/verkleinerten Speicherblock zurück.  Da der Speicher nicht verschoben wird, ist die Adresse identisch mit "userData".  Wenn ein Fehler aufgetreten ist oder der Block nicht auf die angeforderte Größe erweitert werden konnte, wird `NULL` zurückgegeben.  Wenn ein Fehler auftritt, wird `errno` mit Informationen des Betriebssystems über die Art des Fehlers angegeben.  Weitere Informationen zu `errno` finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die Funktion `_expand_dbg` ist eine Debugversion der [expand](../../c-runtime-library/reference/expand.md)\-Funktion.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder Aufruf von `_expand_dbg`  zu einem Aufruf von `_expand` reduziert.  Sowohl `_expand` als auch `_expand_dbg` ändern die Größe eines Speicherblocks im Basisheap, jedoch verfügt `_expand_dbg` über mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzerteils des Blocks zum Prüfen auf Speicherverluste, einen Blocktypparameter zum Nachverfolgen von bestimmten Belegungstypen und `filename`\/`linenumber`\-Informationen zum Ermitteln des Ursprungs von Belegungsanforderungen.  
  
 `_expand_dbg` ändert die Größe des angegebenen Speicherblocks mit etwas mehr Speicherplatz als der angeforderten `newSize`.  `newSize` kann größer oder kleiner sein als die Größe des ursprünglich belegten Speicherblocks.  Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen.  Die Größenänderung wird erreicht, indem der ursprüngliche Speicherblock erweitert oder verkürzt wird.  Im Gegensatz zur [\_realloc\_dbg](../../c-runtime-library/reference/realloc-dbg.md)\-Funktion verschiebt `_expand_dbg` nicht den Speicherblock.  
  
 Wenn `newSize` größer als die ursprüngliche Blockgröße ist, wird der Speicherblock erweitert.  Wenn während einer Erweiterung der Speicherblock nicht auf die angeforderte Größe erweitert werden kann, wird `NULL` zurückgegeben.  Wenn `newSize` kleiner als die ursprüngliche Blockgröße ist, wird der Speicherblock verkürzt, bis die neue Größe erreicht wurde.  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  Weitere Informationen zu den Zuordnungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapreservierungsfunktionen](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
 Diese Funktion überprüft ihre Parameter.  Wenn `memblock` ein NULL\-Zeiger ist oder die Größe `_HEAP_MAXREQ` überschreitet, ruft diese Funktion einen Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `NULL` zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_expand_dbg`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_expand_dbg.c  
//  
// This program allocates a block of memory using _malloc_dbg  
// and then calls _msize_dbg to display the size of that block.  
// Next, it uses _expand_dbg to expand the amount of  
// memory used by the buffer and then calls _msize_dbg again to  
// display the new amount of memory allocated to the buffer.  
//  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
   long *buffer;  
   size_t size;  
  
   // Call _malloc_dbg to include the filename and line number  
   // of our allocation request in the header  
   buffer = (long *)_malloc_dbg( 40 * sizeof(long),  
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if( buffer == NULL )  
      exit( 1 );  
  
   // Get the size of the buffer by calling _msize_dbg  
   size = _msize_dbg( buffer, _NORMAL_BLOCK );  
   printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );  
  
   // Expand the buffer using _expand_dbg and show the new size  
   buffer = (long *)_expand_dbg( buffer, size + sizeof(long),  
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );  
  
   if( buffer == NULL )  
      exit( 1 );  
   size = _msize_dbg( buffer, _NORMAL_BLOCK );  
   printf( "Size of block after _expand_dbg of 1 more long: %u\n",  
           size );  
  
   free( buffer );  
   exit( 0 );  
}  
```  
  
  **Größe des Blocks nach "\_malloc\_dbg" von 40 Long\-Zeichen: 160**  
**Größe des Blockes nach "\_expand\_dbg" von 1 Long\-Zeichen mehr: 164**   
## Kommentar  
 Die Ausgabe dieses Programms hängt von der Funktionalität des Computers ab, ob alle Abschnitte erweitert werden können.  Wenn alle Abschnitte erweitert wurden, wird die Ausgabe im Ausgabeabschnitt wiedergegeben.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)