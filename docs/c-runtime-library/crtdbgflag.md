---
title: "_crtDbgFlag | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_crtDbgFlag"
  - "crtDbgFlag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_crtDbgFlag-Konstante"
  - "crtDbgFlag-Konstante"
  - "Debugheap, Steuerungskennzeichen"
  - "Debugheap, Nachverfolgen von Arbeitsspeicher auf"
  - "Aktivieren des Nachverfolgungskennzeichens für die Arbeitsspeicherbelegung"
  - "Speicherreservierung, Nachverfolgungskennzeichen"
  - "Speicher, Nachverfolgen auf dem Debugheap"
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _crtDbgFlag
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Flag **\_crtDbgFlag** besteht aus fünf Bitfeldern, die steuern, wie Speicherbelegungen in der Debugversion des Heaps nachverfolgt, geprüft, gemeldet und als Dump ausgegeben werden.  Die Bitfelder des Flags werden mithilfe der Funktion [\_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) festgelegt.  Dieses Flag und seine Bitfelder werden in Crtdbg.h deklariert.  Dieses Flag ist nur verfügbar, wenn das Flag [\_DEBUG](../c-runtime-library/debug.md) in der Anwendung definiert wurde.  
  
 Weitere Informationen zur Verwendung dieses Flags in Verbindung mit anderen Debugfunktionen finden Sie unter [Berichtsfunktionen für den Heapzustand](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Heap_State_Reporting_Functions).  
  
## Siehe auch  
 [Steuerungsflags](../c-runtime-library/control-flags.md)