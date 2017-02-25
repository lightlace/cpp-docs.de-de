---
title: "_CrtGetAllocHook | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtGetAllocHook"
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
  - "CrtGetAllocHook"
  - "_CrtGetAllocHook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CrtGetAllocHook-Funktion"
  - "CrtGetAllocHook-Funktion"
ms.assetid: 036acf7c-547a-4b3f-a636-80451070d7ed
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _CrtGetAllocHook
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die aktuelle clientdefinierte Zuordnungsfunktion zur Verknüpfung mit dem Speicherbelegungsprozess der C\-Laufzeit ab \(nur Debugversion\).  
  
## Syntax  
  
```  
_CRT_ALLOC_HOOK _CrtGetAllocHook( void );  
```  
  
## Rückgabewert  
 Gibt die momentan definierten Reservierungshookfunktion zurück.  
  
## Hinweise  
 `_CrtGetAllocHook` ruft die aktuelle clientdefinierte Anwendungshookfunktion für den Debugbibliothek\-Speicherbelegungsprozess der C\-Laufzeit ab.  
  
 Weitere Informationen zur Verwendung anderer hookfähiger Laufzeitfunktionen und zum Schreiben eigener clientdefinierter Hookfunktionen finden Sie unter [Schreiben von Hookfunktionen zum Debuggen](../Topic/Debug%20Hook%20Function%20Writing.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_CrtGetAllocHook`|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [\_CrtSetAllocHook](../../c-runtime-library/reference/crtsetallochook.md)