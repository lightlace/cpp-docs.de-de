---
title: "&quot;Sub New&quot; kann keine Schnittstellenmember implementieren."
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
  - "bc31042"
  - "vbc31042"
helpviewer_keywords: 
  - "BC31042"
ms.assetid: 43ad231f-878d-4d08-b43c-06bf167ddd7d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Sub New&quot; kann keine Schnittstellenmember implementieren.
`Sub New` ist ein Konstruktor und kann keine Member implementieren.  
  
 **Fehler\-ID:** BC31042  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie `Implements`\-Anweisungen aus `Sub New`\-Prozeduren.  
  
## Siehe auch  
 [Interfaces](../Topic/Interfaces%20\(Visual%20Basic\).md)   
 [Implements](../Topic/Implements%20Clause%20\(Visual%20Basic\).md)