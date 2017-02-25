---
title: "_query_new_mode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_query_new_mode"
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
  - "query_new_mode"
  - "_query_new_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_query_new_mode-Funktion"
  - "Handlermodi"
  - "query_new_mode-Funktion"
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# _query_new_mode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt eine ganze Zahl zurück, die den neuen Handlermodus angibt, der durch `_set_new_mode` für `malloc` festgelegt wird.  
  
## Syntax  
  
```  
  
      int _query_new_mode(  
   void   
);  
```  
  
## Rückgabewert  
 Gibt den neuen aktuellen Handlermodus, nämlich 0 oder 1, für `malloc` zurück.  Ein Rückgabewert 1 gibt an, dass, auf Speicher zu belegen, kann `malloc` die neue Handlerroutine aufruft; ein Rückgabewert 0 gibt an, dass es nicht mögen.  
  
## Hinweise  
 Die Funktion C\+\+ `_query_new_mode` gibt eine ganze Zahl zurück, die den neuen Handlermodus angibt, der von der Funktion C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) für [malloc](../../c-runtime-library/reference/malloc.md) festgelegt wird.  Der neue Handlermodus gibt an, ob auf, dass Speicher reserviert, `malloc`, die neue Handlerroutine wie Sie mit [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md) aufzurufen ist.  Standardmäßig ruft `malloc` nicht die neue Handlerroutine Fehler auf.  Sie können `_set_new_mode` verwenden, um dieses Verhalten zu überschreiben, sodass auf Fehler `malloc` die neue Handlerroutine genauso aufruft, dass der Operator **neu** der Fall ist, wenn sie zur Speicherbelegung nicht kann.  Weitere Informationen finden Sie in [Operator](../../misc/operator-delete-function.md) und [Operator neu](../../misc/operator-new-function.md)\-Funktionen *der C\+\+\-Sprachreferenz*.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_query_new_mode`|\<new.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_query\_new\_handler](../../c-runtime-library/reference/query-new-handler.md)