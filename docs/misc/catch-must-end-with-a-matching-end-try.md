---
title: "&quot;Catch&quot; muss mit einem entsprechenden &quot;End Try&quot; abgeschlossen werden."
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
  - "bc30441"
  - "vbc30441"
helpviewer_keywords: 
  - "BC30441"
ms.assetid: 0e4756b4-1f29-4073-88c5-8f8c93ba6c9e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Catch&quot; muss mit einem entsprechenden &quot;End Try&quot; abgeschlossen werden.
Im Code wird eine `Catch`\-Anweisung ohne zugehörige `End Try`\-Anweisung verwendet.`Catch`\-Anweisungen müssen mit einer `End Try`\-Anweisung abgeschlossen werden.  
  
 **Fehler\-ID:** BC30441  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die `Catch`\-Anweisung.  
  
2.  Fügen Sie eine `End Try`\-Anweisung hinzu, um den Block zu beenden.  
  
## Siehe auch  
 [Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md)   
 [Übersicht über die strukturierte Ausnahmebehandlung für Visual Basic](assetId:///bb81af80-a735-4873-9711-6151a48e418a)