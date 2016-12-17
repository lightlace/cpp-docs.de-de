---
title: "&quot;Finally&quot; muss mit einem entsprechenden &quot;End Try&quot; abgeschlossen werden"
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
  - "vbc30442"
  - "bc30442"
helpviewer_keywords: 
  - "BC30442"
ms.assetid: 36cce657-186c-4ba0-a760-abcef9529f18
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Finally&quot; muss mit einem entsprechenden &quot;End Try&quot; abgeschlossen werden
Im Code wird eine `Finally`\-Anweisung ohne zugehörige `End Try`\-Anweisung verwendet.`Finally`\-Anweisungen müssen mit einer `End Try`\-Anweisung abgeschlossen werden.  
  
 **Fehler\-ID:** BC30442  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die `Finally`\-Anweisung.  
  
2.  Fügen Sie eine `End Try`\-Anweisung hinzu, um den Block zu beenden.  
  
## Siehe auch  
 [Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md)   
 [Übersicht über die strukturierte Ausnahmebehandlung für Visual Basic](assetId:///bb81af80-a735-4873-9711-6151a48e418a)