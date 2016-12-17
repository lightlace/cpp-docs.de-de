---
title: "Gespeicherte Register von Aufrufer/Aufgerufenem"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Gespeicherte Register von Aufrufer/Aufgerufenem
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Register RAX, RCX, RDX, R8, R9, R10, R11 werden als flüchtig betrachtet und müssen bei Funktionsaufrufen als undefiniert betrachtet werden \(sofern ein gesicherter Zusatnd nicht durch Analysen, z. B. eine vollständige Programmoptimierung, nachgewiesen wird\).  
  
 Die Register RBX, RBP, RDI, RSI, RSP, R12, R13, R14 und R15 werden als nicht flüchtig betrachtet und müssen vor der Verwendung durch eine Funktion gesichert und wiederhergestellt werden.  
  
## Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)