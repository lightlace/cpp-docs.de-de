---
title: "Ausdrucksanweisung | Microsoft Docs"
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
  - "Ausdrucksanweisungen"
  - "Anweisungen, Ausdruck"
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausdrucksanweisung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ausdrucksanweisungen bewirken die Auswertung von Ausdrücken.  Keine Übertragung der Steuerung oder Iteration tritt infolge einer Ausdrucksanweisung auf.  
  
 Die Syntax für die Ausdrucksanweisung ist einfach  
  
## Syntax  
  
```  
[expression ] ;  
```  
  
## Hinweise  
 Alle Ausdrücke in einer Ausdrucksanweisung werden ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor die nächste Anweisung ausgeführt wird.  Die häufigsten Ausdrucksanweisungen sind Zuweisungen und Funktionsaufrufe.  Wenn der Ausdruck optional ist, wird ein Semikolon allein als eine leere Ausdrucksanweisung betrachtet, die als [NULL](../cpp/null-statement.md)\-Anweisung bezeichnet wird.  
  
## Siehe auch  
 [Übersicht über C\+\+\-Anweisungen](../cpp/overview-of-cpp-statements.md)