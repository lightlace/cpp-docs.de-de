---
title: "Naked-Funktionsaufrufe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Epilogcode"
  - "naked-Funktionen"
  - "naked-Schlüsselwort [C++]"
  - "naked-Schlüsselwort [C++], Speicherklassenattribut"
  - "Prologcode"
  - "Virtuelle Gerätetreiber"
  - "Virtuelle Gerätetreiber, naked-Funktionsaufrufe"
  - "VXD (virtuelle Gerätetreiber)"
ms.assetid: 2a66847a-a43f-4541-a7be-c9f5f29b5fdb
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Naked-Funktionsaufrufe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Funktionen, die mit dem `naked`\-Attribut deklariert werden, werden ohne Prolog\- oder Epilogcode ausgegeben und ermöglichen es Ihnen, eigene benutzerdefinierte Prolog\-\/Epilogsequenzen mit [Inlineassembler](../assembler/inline/inline-assembler.md) zu schreiben.  Naked\-Funktionen werden als erweiterte Funktion bereitgestellt.  Sie ermöglichen es Ihnen, eine Funktion zu deklarieren, die von einem anderen Kontext als C\/C\+\+ aufgerufen wird, und somit andere Annahmen darüber trifft, wo die Parameter sind oder welche Register beibehalten werden.  Zu den Beispielen zählen Routinen wie Interrupthandler.  Diese Funktion ist für Writer von virtuellen Gerätetreibern \(VxDs\) besonders nützlich.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [naked](../cpp/naked-cpp.md)  
  
-   [Regeln und Einschränkungen für Naked\-Funktionen](../cpp/rules-and-limitations-for-naked-functions.md)  
  
-   [Überlegungen für das Schreiben des Prolog\-\/Epilogcodes](../cpp/considerations-for-writing-prolog-epilog-code.md)  
  
### END Microsoft\-spezifisch  
  
## Siehe auch  
 [Aufrufkonventionen](../cpp/calling-conventions.md)