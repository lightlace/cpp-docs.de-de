---
title: "_query_new_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_query_new_handler"
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
  - "_query_new_handler"
  - "query_new_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_query_new_handler-Funktion"
  - "Fehlerbehandlung"
  - "Handlerroutinen"
  - "query_new_handler-Funktion"
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# _query_new_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die Adresse der aktuellen neuen Handlerroutine zurück.  
  
## Syntax  
  
```  
  
      _PNH _query_new_handler(  
   void   
);  
```  
  
## Rückgabewert  
 Gibt die Adresse der aktuellen und neuen Handlerroutine wie von `_set_new_handler` zurück.  
  
## Hinweise  
 Die Funktion C\+\+ `_query_new_handler` gibt die Adresse des aktuellen Ausnahmebehandlungsfunktionssatzes von der Funktion C\+\+ [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md) zurück.  `_set_new_handler` wird verwendet, um eine Ausnahmebehandlungsfunktion anzugeben, die, Steuerelement zu erhalten ist, wenn der **neu**\-Operator Belegen nicht kann.  Weitere Informationen finden Sie in Diskussionen über die [Operator neu](../../misc/operator-new-function.md) und [Operator](../../misc/operator-delete-function.md)\-Funktionen *der C\+\+\-Sprachreferenz*.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_query_new_handler`|\<new.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Speicherbelegung](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)