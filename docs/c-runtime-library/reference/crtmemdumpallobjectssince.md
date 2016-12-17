---
title: "_CrtMemDumpAllObjectsSince"
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
  - "_CrtMemDumpAllObjectsSince"
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
  - "CrtMemDumpAllObjectsSince"
  - "_CrtMemDumpAllObjectsSince"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtMemDumpAllObjectsSince-Funktion"
  - "CrtMemDumpAllObjectsSince-Funktion"
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# _CrtMemDumpAllObjectsSince
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt Informationen zu Objekten im Heap ab Beginn der Programmausführung oder ab einem angegebenen Heapzustand aus \(nur Debugversion\).  
  
## Syntax  
  
```  
  
      void _CrtMemDumpAllObjectsSince(   
   const _CrtMemState *state   
);  
```  
  
#### Parameter  
 `state`  
 Zeiger zum Heapzustand, ab dem die Ausgabe erfolgen soll, oder **NULL**.  
  
## Hinweise  
 Die `_CrtMemDumpAllObjectsSince`\-Funktion gibt die Debugheaderinformationen von Objekten, die im Heap zugeordnet sind, in einer für den Benutzer lesbaren Formular aus.  Die Dumpinformationen können von der Anwendung zum Nachverfolgen von Zuordnungen und zum Erkennen von Speicherproblemen verwendet werden.  Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtMemDumpAllObjectsSince` während der Vorverarbeitung entfernt.  
  
 `_CrtMemDumpAllObjectsSince` verwendet den Wert des `state`\-Parameters, um zu ermitteln, wo der Dumpvorgang initiiert werden soll.  Um die Ausgabe ab einem angegebenen Heapzustand zu beginnen, muss der `state`\-Parameter ein Zeiger zu einer **\_CrtMemState**\-Struktur sein, die vor dem Aufruf von `_CrtMemDumpAllObjectsSince` durch [\_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) gefüllt wurde.  Wenn der `state`\-Parameter **NULL** ist, startet die Funktion die Ausgabe ab Beginn der Programmausführung.  
  
 Wenn die Anwendung eine Dumphookfunktion durch Aufrufen von [\_CrtSetDumpClient](../../c-runtime-library/reference/crtsetdumpclient.md) installiert hat, wird die von der Anwendung bereitgestellte Dumpfunktion ebenfalls aufgerufen, wenn `_CrtMemDumpAllObjectsSince` Informationen zu einem `_CLIENT_BLOCK`\-Blocktyp ausgibt.  Standardmäßig sind interne C\-Laufzeitblöcke \(`_CRT_BLOCK`\) nicht in Speicherabbildvorgängen enthalten.  Die [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)\-Funktion kann zum Aktivieren des `_CRTDBG_CHECK_CRT_DF`\-Bits von **\_crtDbgFlag** verwendet werden, um diese Blöcke einzuschließen.  Außerdem werden die Blöcke, die als "freigegeben" oder "ignoriert" markiert wurden \(**\_FREE\_BLOCK**, **\_IGNORE\_BLOCK**\) nicht im Speicherabbild berücksichtigt.  
  
 Weitere Informationen über Heapzustandsfunktionen und die `_CrtMemState`\-Struktur finden Sie unter [Berichtsfunktionen für den Heapzustand](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions).  Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|**\_CrtMemDumpAll\-ObjectsSince**|\<crtdbg.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Nur Debugversionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Ein Beispiel für die Verwendung von `_CrtMemDumpAllObjectsSince` finden Sie unter [crt\_dbg2](assetId:///21e1346a-6a17-4f57-b275-c76813089167).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)