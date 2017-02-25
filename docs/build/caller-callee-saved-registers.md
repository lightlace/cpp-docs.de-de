---
title: "Gespeicherte Register von Aufrufer/Aufgerufenem | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Gespeicherte Register von Aufrufer/Aufgerufenem
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Register RAX, RCX, RDX, R8, R9, R10, R11 werden als flüchtig betrachtet und müssen bei Funktionsaufrufen als undefiniert betrachtet werden \(sofern ein gesicherter Zusatnd nicht durch Analysen, z. B. eine vollständige Programmoptimierung, nachgewiesen wird\).  
  
 Die Register RBX, RBP, RDI, RSI, RSP, R12, R13, R14 und R15 werden als nicht flüchtig betrachtet und müssen vor der Verwendung durch eine Funktion gesichert und wiederhergestellt werden.  
  
## Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)