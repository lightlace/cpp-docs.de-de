---
title: "Ausdrucksauswertung (C) | Microsoft Docs"
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
helpviewer_keywords: 
  - "Ausdrucksauswertung"
  - "Ausdrücke [C++], Auswerten"
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausdrucksauswertung (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ausdrücke, die mit Zuweisung, unärem Inkrement bzw. unärem Dekrement zusammenhängen oder eine Funktion aufrufen, können Folgen haben, die mit ihrer Auswertung auftreten \(Nebeneffekte\).  Mit dem Erreichen eines "Sequenzpunkts" wird gewährleistet, dass alles vor dem Sequenzpunkt, einschließlich aller möglichen Nebeneffekte, ausgewertet wurde, bevor die Auswertung von Elementen nach dem Sequenzpunkt fortgesetzt wird.  
  
 "Nebeneffekte" sind die Änderungen, die durch die Auswertung eines Ausdrucks verursacht werden.  Nebeneffekte treten auf, wenn der Wert einer Variablen durch eine Ausdrucksauswertung geändert wird.  Alle Zuweisungsvorgänge haben Nebeneffekte.  Funktionsaufrufe können auch Nebeneffekte haben, wenn sie den Wert eines extern sichtbaren Elements entweder durch direkte oder indirekte Zuweisung über einen Zeiger ändern.  
  
## Siehe auch  
 [Operanden und Ausdrücke](../c-language/operands-and-expressions.md)