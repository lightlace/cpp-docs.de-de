---
title: "„Case“ kann nur innerhalb einer „Select Case“-Anweisung verwendet werden."
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
  - "vbc30072"
  - "bc30072"
helpviewer_keywords: 
  - "BC30072"
ms.assetid: da808bc3-f154-444a-b547-3cf55beff8a9
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# „Case“ kann nur innerhalb einer „Select Case“-Anweisung verwendet werden.
Eine `Case`\-Anweisung befindet sich außerhalb eines `Select`\-Blocks. Eine `Case`\-Anweisung kann nur zwischen einer `Select`\- oder `Select Case`\-Anweisung und der entsprechenden `End Select`\-Anweisung verwendet werden.  
  
 **Fehler\-ID:** BC30072  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die `Case`\-Anweisung, oder verschieben Sie sie in einen `Select`\- Block.  
  
## Siehe auch  
 [Select...Case Statement](../Topic/Select...Case%20Statement%20\(Visual%20Basic\).md)