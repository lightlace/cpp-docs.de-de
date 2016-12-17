---
title: "_CrtMemDumpStatistics"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_CrtMemDumpStatistics"
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
  - "CrtMemDumpStatistics"
  - "_CrtMemDumpStatistics"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtMemDumpStatistics-Funktion"
  - "CrtMemDumpStatistics-Funktion"
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# _CrtMemDumpStatistics
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die Debugheaderinformationen für einen angegebenen Heapzustand in einer für den Benutzer lesbaren Form aus \(nur Debugversion\).  
  
## Syntax  
  
```  
void _CrtMemDumpStatistics(   
   const _CrtMemState *state   
);  
```  
  
#### Parameter  
 `state`  
 Zeiger zum auszugebenden Heapzustand.  
  
## Hinweise  
 Die `_CrtMemDumpStatistics`\-Funktion gibt die Debugheaderinformationen für einen angegebenen Zustand des Heaps in einer für den Benutzer lesbaren Form aus. Die Dumpstatistik kann von der Anwendung zum Nachverfolgen von Zuordnungen und zum Erkennen von Speicherproblemen verwendet werden. Der Speicherzustands kann einen bestimmten Heapzustand oder den Unterschied zwischen zwei Zuständen enthalten. Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtMemDumpStatistics` während der Vorverarbeitung entfernt.  
  
 Der `state`\-Parameter muss ein Zeiger auf eine `_CrtMemState`\-Struktur sein, die von [\_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) gefüllt oder von [\_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) zurückgegeben wurden, bevor `_CrtMemDumpStatistics` aufgerufen wird. Wenn `state` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt und keine Aktion durchgeführt. Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Weitere Informationen über Heapzustandsfunktionen und die `_CrtMemState`\-Struktur finden Sie unter [Heap State Reporting Functions](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionale Header|  
|-------------|---------------------------|----------------------|  
|`_CrtMemDumpStatistics`|\<crtdbg.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
 **Bibliotheken:** nur Debugversionen von [CRT\-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 <xref:System.Diagnostics.PerformanceCounter?displayProperty=fullName>  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)