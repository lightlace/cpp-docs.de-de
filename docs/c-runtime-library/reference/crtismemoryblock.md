---
title: "_CrtIsMemoryBlock"
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
  - "_CrtIsMemoryBlock"
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
  - "CrtlsMemoryBlock"
  - "_CrtIsMemoryBlock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtIsMemoryBlock-Funktion"
  - "CrtIsMemoryBlock-Funktion"
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# _CrtIsMemoryBlock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überprüft, ob sich ein angegebener Speicherblock im lokalen Heap befindet und ob er einen gültigen Debugheap\-Blocktypbezeichner hat \(nur Debugversion\).  
  
## Syntax  
  
```  
int _CrtIsMemoryBlock(   
   const void *userData,  
   unsigned int size,  
   long *requestNumber,  
   char **filename,  
   int *linenumber   
);  
```  
  
#### Parameter  
 \[in\] `userData`  
 Zeiger auf den Anfang des zu überprüfenden Speicherblocks.  
  
 \[in\] `size`  
 Größe des angegebenen Blocks \(in Bytes\).  
  
 \[out\] `requestNumber`  
 Zeiger zur Belegungsnummer des Blocks oder `NULL`.  
  
 \[out\] `filename`  
 Zeiger zum Namen der Quelldatei, der den Block angefordert hat, oder `NULL`.  
  
 \[out\] `linenumber`  
 Zeiger zur Zeilennummer in der Quelldatei oder `NULL`.  
  
## Rückgabewert  
 `_CrtIsMemoryBlock` gibt `TRUE` zurück, wenn sich der angegebene Speicherblock im lokalen Heap befindet und über einen gültigen Debugheap\-Blocktypbezeichner verfügt. Andernfalls gibt die Funktion `FALSE` zurück.  
  
## Hinweise  
 Die `_CrtIsMemoryBlock`\-Funktion überprüft, ob sich ein angegebener Speicherblock im lokalen Heap der Anwendung befindet und ob sie einen gültigen Blocktypbezeichner hat.  Diese Funktion kann auch verwendet werden, um die Bestellnummer der Objektzuordnung und den Quelldateinamen\/die Zeilennummer abzurufen, wo die Speicherblockbelegung ursprünglich angefordert wurde.  Die Übergabe von Werten ungleich NULL für den `requestNumber`\-, `filename`\- oder `linenumber`\-Parameter führt dazu, dass `_CrtIsMemoryBlock` diese Parameter auf die Werte im Debugheader des Speicherblocks festlegt, wenn der Block im lokalen Heap gefunden wird.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtIsMemoryBlock` während der Vorverarbeitung entfernt.  
  
 Wenn `_CrtIsMemoryBlock` fehlschlägt, wird `FALSE` zurückgegeben und die Ausgabeparameter werden auf die Standardwerte initialisiert: `requestNumber` und `lineNumber` werden auf 0 und `filename` wird auf `NULL` eingestellt.  
  
 Da diese Funktion `TRUE` oder `FALSE` zurückgibt, kann sie an eine der [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)\-Makros übergeben werden, um einen einfachen Debug\-Fehlerbehandlungsmechanismus zu erstellen.  Im folgenden Beispiel wird ein Assertionsfehler ausgelöst, wenn sich die angegebene Adresse nicht im lokalen Heap befindet:  
  
```  
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,   
&filename, &linenumber ) );  
```  
  
 Weitere Informationen dazu, wie `_CrtIsMemoryBlock` mit anderen Debugfunktionen und \-makros verwendet werden kann, finden Sie unter [Makros für die Berichterstellung](../Topic/Macros%20for%20Reporting.md).  Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_CrtIsMemoryBlock`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Weitere Informationen hierzu finden Sie im Beispiel für das Thema [\_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)