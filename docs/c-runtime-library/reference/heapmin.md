---
title: "_heapmin | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_heapmin"
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
  - "_heapmin"
  - "heapmin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_heapmin-Funktion"
  - "Heapspeicher"
  - "heapmin-Funktion"
  - "Heaps, Freigeben von nicht verwendetem Arbeitsspeicher"
  - "Speicher, Freigeben"
  - "Minimieren von Heaps"
ms.assetid: c0bccdf6-2d14-4d7b-a7ff-d6a17bdb410f
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _heapmin
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt nicht verwendeten Heapspeicher das Betriebssystem frei.  
  
## Syntax  
  
```  
int _heapmin( void );  
```  
  
## Rückgabewert  
 Wenn erfolgreich, `_heapmin` gibt 0 zurück; Andernfalls wird die Funktion \- 1 zurück und legt `errno` auf `ENOSYS` fest.  
  
 Weitere Informationen über diese und andere Rückgabecodes, finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `_heapmin`\-Funktion können den Heap, indem nicht verwendete Heapspeicher auf das Betriebssystem freigibt.  Wenn das Betriebssystem nicht `_heapmin`, \(z Windows 98\) unterstützt, wird die Funktion \- 1 zurück und legt `errno` auf `ENOSYS` fest.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_heapmin`|\<malloc.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [\_heapadd](../../c-runtime-library/heapadd.md)   
 [\_heapchk](../../c-runtime-library/reference/heapchk.md)   
 [\_heapset](../../c-runtime-library/heapset.md)   
 [\_heapwalk](../../c-runtime-library/reference/heapwalk.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)