---
title: "_aligned_offset_malloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_offset_malloc_dbg"
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
  - "_aligned_offset_malloc_dbg"
  - "aligned_offset_malloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_offset_malloc_dbg-Funktion"
  - "aligned_offset_malloc_dbg-Funktion"
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _aligned_offset_malloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Belegt Speicher in einer angegebenen Ausrichtungsgrenze \(nur Debugversion\).  
  
## Syntax  
  
```  
void * _aligned_offset_malloc_dbg(  
   size_t size,   
   size_t alignment,   
   size_t offset,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### Parameter  
 \[in\] `size`  
 Die Größe der angeforderten Speicherbelegung.  
  
 \[in\] `alignment`  
 Der Ausrichtungswert, der eine ganzzahlige Potenz von 2 sein muss.  
  
 \[in\] `offset`  
 Der Offset in der Speicherbelegung zum Erzwingen der Ausrichtung.  
  
 \[in\] `filename`  
 Zeiger zum Namen der Quelldatei, der die Belegung angefordert hat, oder NULL.  
  
 \[in\] `linenumber`  
 Zeilennummer in der Quelldatei, in der die Belegung angefordert wurde, oder NULL.  
  
## Rückgabewert  
 Ein Zeiger zum Speicherblock, der belegt wurde, oder `NULL` bei fehlgeschlagenem Vorgang.  
  
## Hinweise  
 `_aligned_offset_malloc_dbg` ist eine Debugversion der [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md)\-Funktion.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder Aufruf von `_aligned_offset_malloc_dbg` zu einem Aufruf von `_aligned_offset_malloc` reduziert.  Sowohl `_aligned_offset_malloc` als auch `_aligned_offset_malloc_dbg` belegen einen Speicherblock im Basisheap, jedoch bietet `_aligned_offset_malloc_dbg` mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzerteils des Blocks zum Prüfen auf Speicherverluste, einen Blocktypparameter zum Nachverfolgen von bestimmten Belegungstypen und `filename`\/`linenumber`\-Informationen zum Ermitteln des Ursprungs von Belegungsanforderungen.  
  
 `_aligned_offset_malloc_dbg` belegt den Speicherblock mit etwas mehr Speicherplatz als der angeforderten `size`.  Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen.  Wenn der Block belegt wurde, wird der Benutzerteil des Blocks mit dem Wert "0xCD" gefüllt, und jeder der Überschreibungspuffer wird mit "0xFD" gefüllt.  
  
 `_aligned_offset_malloc_dbg` ist nützlich in Situationen, in denen eine Ausrichtung für ein geschachteltes Element erforderlich ist, beispielsweise wenn eine Ausrichtung für eine geschachtelte Klasse erforderlich war.  
  
 `_aligned_offset_malloc_dbg` basiert auf `malloc`. Weitere Informationen finden Sie unter [malloc](../../c-runtime-library/reference/malloc.md).  
  
 Diese Funktion legt `errno` auf `ENOMEM` fest, wenn die Speicherbelegung fehlgeschlagen ist oder die angeforderte Größe größer als `_HEAP_MAXREQ` war.  Weitere Informationen zu `errno` finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  Darüber hinaus überprüft `_aligned_offset_malloc` auch die eigenen Parameter.  Wenn `alignment` keine Potenz von 2 ist oder `offset` größer als oder gleich `size` und ungleich 0 ist, ruft diese Funktion den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `NULL` zurück und stellt `errno` auf `EINVAL` ein.  
  
 Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Weitere Informationen zu den Zuordnungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_aligned_offset_malloc_dbg`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)