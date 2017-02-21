---
title: "_CrtMemCheckpoint | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtMemCheckpoint"
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
  - "CrtMemCheckpoint"
  - "_CrtMemCheckpoint"
  - "crtdbg/_CrtMemCheckpoint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CrtMemCheckpoint-Funktion"
  - "_CrtMemCheckpoint-Funktion"
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _CrtMemCheckpoint
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den aktuellen Zustand des Debugheaps ab und speichert ihn in einer von der Anwendung bereitgestellten `_CrtMemState`\-Struktur \(nur Debugversion\).  
  
## Syntax  
  
```  
void _CrtMemCheckpoint(  
   _CrtMemState *state   
);  
```  
  
#### Parameter  
 `state`  
 Zeiger auf die `_CrtMemState`\-Struktur, die mit dem Arbeitsspeicherprüfpunkt ausgefüllt werden soll.  
  
## Hinweise  
 Die `_CrtMemCheckpoint`\-Funktion erstellt eine Momentaufnahme des aktuellen Zustands des Debugheaps eines beliebigen Moments. Diese Momentaufnahme kann von anderen Heapzustandsfunktionen wie [\_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md) verwendet werden, um das Erkennen von Speicherverlusten und anderen Problemen zu unterstützen. Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtMemState` während der Vorverarbeitung entfernt.  
  
 Die Anwendung muss einen Zeiger zu einer bereits zugeordneten Instanz der `_CrtMemState`\-Struktur, die in Crtdbg.h definiert ist, im `state`\-Parameter übergeben. Wenn `_CrtMemCheckpoint` bei der Prüfpunkterstellung einen Fehler erkennt, generiert die Funktion einen `_CRT_WARN`\-Debugbericht, der das Problem beschreibt.  
  
 Weitere Informationen über Heapzustandsfunktionen und die `_CrtMemState`\-Struktur finden Sie unter [Berichtsfunktionen für den Heapzustand](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Wenn `state` den Wert `NULL` annimmt, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) auf `EINVAL` gesetzt, und die Funktion kehrt zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_CrtMemCheckpoint`|\<crtdbg.h\>, \<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
 **Bibliotheken:** nur Debugversionen der UCRT.  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [\_CrtMemDifference](../../c-runtime-library/reference/crtmemdifference.md)