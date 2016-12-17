---
title: "&#39;Exit Try&#39; kann nur innerhalb einer Try-Anweisung verwendet werden."
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
  - "vbc30393"
  - "bc30393"
helpviewer_keywords: 
  - "BC30393"
ms.assetid: b8651df3-a32f-478c-a6d8-aa0ef584155f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Exit Try&#39; kann nur innerhalb einer Try-Anweisung verwendet werden.
`Exit Try` kann nur innerhalb einer `Try`\-Blockanweisung angezeigt werden. Entweder ist die `Exit Try`\-Anweisung redundant, oder die `Exit Try`\-Anweisung befindet sich außerhalb des entsprechenden `Try`\-Blocks.  
  
 **Fehler\-ID:** BC30393  
  
### So beheben Sie diesen Fehler  
  
1.  Suchen und entfernen Sie die unnötige `Exit Try`\-Anweisung.  
  
2.  Verschieben Sie die `Exit Try`\-Anweisung an die gewünschte Position im Code.  
  
## Siehe auch  
 [Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md)   
 [Übersicht über die strukturierte Ausnahmebehandlung für Visual Basic](assetId:///bb81af80-a735-4873-9711-6151a48e418a)