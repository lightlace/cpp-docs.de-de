---
title: "_heapchk | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_heapchk"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_heapchk"
  - "heapchk"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_heapchk-Funktion"
  - "Konsistenzüberprüfung von Heaps"
  - "Debuggen [CRT], Heapbezogene Probleme"
  - "heapchk-Funktion"
  - "Heaps, Überprüfen der Konsistenz"
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _heapchk
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt Konsistenzprüfungen auf dem Heap fehl.  
  
## Syntax  
  
```  
int _heapchk( void );  
```  
  
## Rückgabewert  
 `_heapchk` gibt eine der folgenden ganzzahligen Manifestkonstanten zurück, die in Malloc.h definiert sind.  
  
 `_HEAPBADBEGIN`  
 Ursprüngliche Header ist ungültig oder kann nicht gefunden werden.  
  
 `_HEAPBADNODE`  
 Ungültiger Knoten wurde gefunden, Heap oder ist beschädigt.  
  
 `_HEAPBADPTR`  
 Zeiger in Heap ist ungültig.  
  
 `_HEAPEMPTY`  
 Heap kann nicht initialisiert.  
  
 `_HEAPOK`  
 Heap wird, konsistent.  
  
 Wenn ein Fehler auftritt, setzt `_heapchk``errno` zudem auf `ENOSYS`.  
  
## Hinweise  
 Die `_heapchk`\-Funktionshilfen debuggen Heap\-verknüpfte Probleme, indem für minimale Konsistenz des Heaps überprüfen.  Wenn das Betriebssystem nicht `_heapchk`, \(z Windows 98\) unterstützt, wird `_HEAPOK` zurückgegeben und `errno` auf `ENOSYS` fest.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_heapchk`|\<malloc.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_heapchk.c  
// This program checks the heap for  
// consistency and prints an appropriate message.  
  
#include <malloc.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  heapstatus;  
   char *buffer;  
  
   // Allocate and deallocate some memory  
   if( (buffer = (char *)malloc( 100 )) != NULL )  
      free( buffer );  
  
   // Check heap status  
   heapstatus = _heapchk();  
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf(" OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf(" OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
}  
```  
  
  **OK \- Heap ist zwar**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [\_heapadd](../../c-runtime-library/heapadd.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [\_heapset](../../c-runtime-library/heapset.md)   
 [\_heapwalk](../../c-runtime-library/reference/heapwalk.md)