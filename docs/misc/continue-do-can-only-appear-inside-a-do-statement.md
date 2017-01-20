---
title: "&quot;Continue Do&quot; kann nur innerhalb einer Do-Anweisung verwendet werden"
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
  - "vbc30782"
  - "bc30782"
helpviewer_keywords: 
  - "BC30782"
ms.assetid: c6b35e63-4d84-449d-9685-41a1bc0a7f35
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Continue Do&quot; kann nur innerhalb einer Do-Anweisung verwendet werden
Eine `Continue Do`\-Anweisung kann nur innerhalb einer `Do...Loop`\-Schleife verwendet werden.  
  
 **Fehler\-ID:** BC30782  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn sich die `Continue Do`\-Anweisung in einer `For...Next`\-Schleife befindet, müssen Sie die Anweisung in `Continue For` ändern.  
  
2.  Wenn sich die `Continue Do`\-Anweisung in einer `While...End While`\-Schleife befindet, müssen Sie die Anweisung in `Continue While` ändern.  
  
3.  Entfernen Sie andernfalls die `Continue Do`\-Anweisung.  
  
## Siehe auch  
 [Continue Statement](../Topic/Continue%20Statement%20\(Visual%20Basic\).md)   
 [Do...Loop Statement](../Topic/Do...Loop%20Statement%20\(Visual%20Basic\).md)