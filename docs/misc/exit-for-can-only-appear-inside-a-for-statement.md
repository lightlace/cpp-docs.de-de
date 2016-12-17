---
title: "&quot;Exit For&quot; kann nur innerhalb einer For-Anweisung verwendet werden."
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc30096"
  - "vbc30096"
helpviewer_keywords: 
  - "BC30096"
ms.assetid: 1062a329-9364-4234-9175-4c70a51cb7ae
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Exit For&quot; kann nur innerhalb einer For-Anweisung verwendet werden.
Eine `Exit For`\-Anweisung befindet sich außerhalb einer `For`\-Schleife.`Exit For` ist nur zwischen einer `For`\- oder `For Each`\-Anweisung und einer entsprechenden `Next`\-Anweisung gültig.  
  
 **Fehler\-ID:** BC30096  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass eine gültige `For`\- oder `For Each`\-Anweisung vor `Exit For` steht und eine gültige `Next`\-Anweisung darauf folgt.  
  
2.  Stellen Sie sicher, dass andere Steuerungsstrukturen innerhalb der `For`\-Schleife ordnungsgemäß beendet werden.  
  
## Siehe auch  
 [For...Next\-Anweisung](../Topic/For...Next%20Statement%20\(Visual%20Basic\).md)   
 [For Each...Next\-Anweisung](../Topic/For%20Each...Next%20Statement%20\(Visual%20Basic\).md)