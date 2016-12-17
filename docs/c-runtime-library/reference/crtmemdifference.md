---
title: "_CrtMemDifference"
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
  - "_CrtMemDifference"
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
  - "_CrtMemDifference"
  - "CrtMemDifference"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CrtMemDifference-Funktion"
  - "_CrtMemDifference-Funktion"
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# _CrtMemDifference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vergleicht zwei Speicherzustände und gibt die vorhandenen Unterschiede zurück \(nur Debugversion\).  
  
## Syntax  
  
```  
int _CrtMemDifference(   
   _CrtMemState *stateDiff,  
   const _CrtMemState *oldState,  
   const _CrtMemState *newState   
);  
```  
  
#### Parameter  
 `stateDiff`  
 Zeiger auf eine `_CrtMemState`\-Struktur, die zum Speichern der Unterschiede zwischen den beiden \(zurückgegebenen\) Speicherzuständen verwendet wird.  
  
 `oldState`  
 Zeiger auf einen früheren Speicherzustand \(`_CrtMemState`\-Struktur\).  
  
 `newState`  
 Zeiger auf einen späteren Speicherzustand \(`_CrtMemState`\-Struktur\).  
  
## Rückgabewert  
 Wenn die Speicherzustände sich erheblich unterscheiden, gibt `_CrtMemDifference` TRUE zurück. Andernfalls gibt die Funktion FALSE zurück.  
  
## Hinweise  
 Die `_CrtMemDifference`\-Funktion vergleicht `oldState` und `newState` und speichert die vorhandenen Unterschiede in `stateDiff`. Dieser Parameter kann dann von der Anwendung verwendet werden, um Speicherverluste und andere Speicherprobleme zu erkennen. Wenn [\_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von `_CrtMemDifference` während der Vorverarbeitung entfernt.  
  
 `newState` und `oldState` müssen jeweils ein gültiger Zeiger auf eine in „Crtdbg.h“ definierte `_CrtMemState`\-Struktur sein, die von [\_CrtMemCheckpoint](../../c-runtime-library/reference/crtmemcheckpoint.md) gefüllt wurde, bevor `_CrtMemDifference` aufgerufen wird.`stateDiff` muss ein Zeiger auf eine zuvor zugeordnete Instanz der `_CrtMemState`\-Struktur sein. Wenn `stateDiff`, `newState` oder `oldState` den Wert `NULL` aufweisen, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) auf `EINVAL` festgelegt und die Funktion gibt FALSE zurück.  
  
 `_CrtMemDifference` vergleicht die `_CrtMemState`\-Feldwerte der Blöcke in `oldState` mit denen in `newState` und speichert das Ergebnis in `stateDiff`. Wenn sich die Anzahl der zugeordneten Blocktypen oder die Gesamtzahl der zugeordneten Blöcke für jeden Typ in den beiden Speicherzuständen unterscheidet, werden die Zustände als deutlich unterschiedlich bezeichnet. Der Unterschied zwischen der größten Menge, die jemals für beide Zustände gleichzeitig zugeordnet wurde, und der Unterschied zwischen den gesamten Speicherbelegungen für die beiden Zustände werden auch in `stateDiff` gespeichert.  
  
 Standardmäßig sind interne C\-Laufzeitblöcke \(`_CRT_BLOCK`\) nicht in den Speicherzustandsvorgängen enthalten. Mit der [\_CrtSetDbgFlag](../../c-runtime-library/reference/crtsetdbgflag.md)\-Funktion kann das `_CRTDBG_CHECK_CRT_DF`\-Bit von `_crtDbgFlag` aktiviert werden, um diese Blöcke in die Erkennung von Speicherverlusten und andere Speicherzustandsvorgänge einzuschließen. Freigegebene Speicherblöcke \(`_FREE_BLOCK`\) führen nicht dazu, dass `_CrtMemDifference` TRUE zurückgibt.  
  
 Weitere Informationen über Heapzustandsfunktionen und die `_CrtMemState`\-Struktur finden Sie unter [Heap State Reporting Functions](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions). Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [Details zum CRT\-Debugheap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------------|-----------------------|  
|`_CrtMemDifference`|\<crtdbg.h\>|\<errno.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
 **Bibliotheken:** nur Debugversionen von [CRT\-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Debugroutinen](../../c-runtime-library/debug-routines.md)   
 [\_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)