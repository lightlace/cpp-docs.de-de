---
title: "_get_unexpected | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_get_unexpected"
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
  - "__get_unexpected"
  - "_get_unexpected"
  - "get_unexpected"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__get_unexpected-Funktion"
  - "_get_unexpected-Funktion"
  - "get_unexpected-Funktion"
ms.assetid: a5f7a7a0-18e0-485e-953d-db291068a1e8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _get_unexpected
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt der von `unexpected` zurückgegebene aufgerufen werden, Enderoutine.  
  
## Syntax  
  
```  
unexpected_function _get_unexpected( void );  
```  
  
## Rückgabewert  
 Gibt einen Zeiger auf die Funktion zurück, die durch [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md) registriert wird.  Wenn keine Funktion festgelegt wurde, wird der Rückgabewert verwendet werden, um das Standardverhalten wiederherzustellen; Dieser Wert kann NULL.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_get_unexpected`|\<eh.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Ausnahmebehandlungsroutinen](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)   
 [unexpected](../../c-runtime-library/reference/unexpected-crt.md)