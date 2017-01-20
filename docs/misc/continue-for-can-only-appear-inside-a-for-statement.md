---
title: "&quot;Continue For&quot; kann nur innerhalb einer For-Anweisung verwendet werden"
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
  - "bc30783"
  - "vbc30783"
helpviewer_keywords: 
  - "BC30783"
ms.assetid: 70891018-27c8-4d36-b168-8cc7177d70cb
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Continue For&quot; kann nur innerhalb einer For-Anweisung verwendet werden
Eine `Continue For`\-Anweisung kann nur innerhalb einer `For...Next`\-Schleife verwendet werden.  
  
 **Fehler\-ID:** BC30783  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn sich die `Continue For`\-Anweisung in einer `Do...Loop` befindet, müssen Sie die Anweisung in `Continue Do` ändern.  
  
     – oder –  
  
     Wenn sich die `Continue For`\-Anweisung in einer `While...End While`\-Schleife befindet, müssen Sie die Anweisung in `Continue While` ändern.  
  
2.  Entfernen Sie andernfalls die `Continue For`\-Anweisung.  
  
## Siehe auch  
 [Continue Statement](../Topic/Continue%20Statement%20\(Visual%20Basic\).md)   
 [For...Next\-Anweisung](../Topic/For...Next%20Statement%20\(Visual%20Basic\).md)