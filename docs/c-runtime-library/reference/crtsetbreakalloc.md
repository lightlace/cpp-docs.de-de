---
title: "_CrtSetBreakAlloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtSetBreakAlloc"
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
  - "CrtSetBreakAlloc"
  - "_CrtSetBreakAlloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtSetBreakAlloc-Funktion"
  - "CrtSetBreakAlloc-Funktion"
ms.assetid: 33bfc6af-a9ea-405b-a29f-1c2d4d9880a1
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtSetBreakAlloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt einen Haltepunkt für eine angegebene Bestellnummer der Objektzuordnung fest \(nur Debugversion\).  
  
## Syntax  
  
```  
  
long _CrtSetBreakAlloc(     long lBreakAlloc  );  
```  
  
#### Parameter  
 *lBreakAlloc*  
 Zuordnungsbestellnummer, für die der Haltepunkt festzulegen ist.  
  
## Rückgabewert  
 Gibt die vorherige Bestellnummer der Objektzuordnung zurück, die einen festgelegten Haltepunkt hatte.  
  
## Hinweise  
 `_CrtSetBreakAlloc` ermöglicht es einer Anwendung, eine Speicherverlusterkennung durchzuführen, indem an einem bestimmten Punkt der Speicherbelegung angehalten und der Ursprung der Anforderung nachverfolgt wird.  Die Funktion verwendet die sequenzielle Bestellnummer der Objektzuordnung, die dem Speicherblock zugewiesen wird, wenn sie im Heap reserviert wurde.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtSetBreakAlloc` während der Vorverarbeitung entfernt.  
  
 Die Bestellnummer der Objektzuordnung wird im *lRequest*\-Feld der **\_CrtMemBlockHeader**\-Struktur gespeichert, die in "Crtdbg.h" definiert ist.  Wenn Informationen zu einem Speicherblock von einer der Debugdumpfunktionen ausgegeben werden, wird die Nummer in geschweiften Klammern angezeigt, z. B. {36}.  
  
 Weitere Informationen zur möglichen Verwendung von `_CrtSetBreakAlloc` mit anderen Speicherverwaltungsfunktionen finden Sie unter [Nachverfolgen von Heapzuweisungsanforderungen](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Track_Heap_Allocation_Requests).  Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_CrtSetBreakAlloc`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
```  
// crt_setbrkal.c  
// compile with: -D_DEBUG /MTd -Od -Zi -W3 /c /link -verbose:lib -debug  
  
/*  
 * In this program, a call is made to the _CrtSetBreakAlloc routine  
 * to verify that the debugger halts program execution when it reaches  
 * a specified allocation number.  
 */  
  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main( )  
{  
        long allocReqNum;  
        char *my_pointer;  
  
        /*   
         * Allocate "my_pointer" for the first  
         * time and ensure that it gets allocated correctly  
         */  
        my_pointer = malloc(10);  
        _CrtIsMemoryBlock(my_pointer, 10, &allocReqNum, NULL, NULL);  
  
        /*   
         * Set a breakpoint on the allocation request  
         * number for "my_pointer"  
         */  
        _CrtSetBreakAlloc(allocReqNum+2);  
  
        /*   
         * Alternate freeing and reallocating "my_pointer"  
         * to verify that the debugger halts program execution  
         * when it reaches the allocation request  
         */  
        free(my_pointer);  
        my_pointer = malloc(10);  
        free(my_pointer);  
        my_pointer = malloc(10);  
        free(my_pointer);  
}  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)