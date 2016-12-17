---
title: "Operatoren k&#246;nnen nicht als &#39;&lt;Schl&#252;sselwort&gt;&#39; deklariert werden."
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc33013"
  - "bc33013"
helpviewer_keywords: 
  - "BC33013"
ms.assetid: bfd805f4-e30e-4553-9cb7-2690595f0480
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Operatoren k&#246;nnen nicht als &#39;&lt;Schl&#252;sselwort&gt;&#39; deklariert werden.
Ein Operator ist mit einem Schlüsselwort deklariert, das für Operatordefinitionen nicht gültig ist.  
  
 Jeder Operator muss sowohl als [Public](../Topic/Public%20\(Visual%20Basic\).md) als auch als [Shared](../Topic/Shared%20\(Visual%20Basic\).md) deklariert werden. Darüber hinaus muss ein Konvertierungsoperator entweder mit [Widening](../Topic/Widening%20\(Visual%20Basic\).md) oder [Narrowing](../Topic/Narrowing%20\(Visual%20Basic\).md) deklariert werden, aber nicht mit beiden. Eine Operatordefinition kann optional die Schlüsselwörter [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md) oder [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md) enthalten. Keine anderen Schlüsselwörter sind in einem [Operator Statement](../Topic/Operator%20Statement.md) zulässig.  
  
 **Fehler\-ID:** BC33013  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das ungültige Schlüsselwort aus der Operatordefinition.  
  
## Siehe auch  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)