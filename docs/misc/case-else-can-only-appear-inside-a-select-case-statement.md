---
title: "&quot;Case Else&quot; kann nur innerhalb einer &quot;Select Case&quot;-Anweisung verwendet werden."
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
  - "bc30071"
  - "vbc30071"
helpviewer_keywords: 
  - "BC30071"
ms.assetid: 9a4f8ccb-717a-4d18-91b4-4a373202c38a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Case Else&quot; kann nur innerhalb einer &quot;Select Case&quot;-Anweisung verwendet werden.
Eine `Case Else`\-Anweisung tritt außerhalb eines `Select`\-Blocks auf. Eine `Case Else`\-Anweisung kann nur zwischen einer `Select`\-Anweisung oder einer `Select Case`\-Anweisung und ihrer entsprechenden `End Select`\-Anweisung verwendet werden.  
  
 **Fehler\-ID:** BC30071  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die `Case Else`\-Anweisung, oder verschieben Sie sie innerhalb eines `Select`\-Blocks.  
  
## Siehe auch  
 [Select...Case Statement](../Topic/Select...Case%20Statement%20\(Visual%20Basic\).md)