---
title: "Delegaten k&#246;nnen keine Schnittstellenmethoden implementieren"
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
  - "bc30018"
  - "vbc30018"
helpviewer_keywords: 
  - "BC30018"
ms.assetid: 71851072-c0c7-4131-aaf7-f3e9e6a2a448
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Delegaten k&#246;nnen keine Schnittstellenmethoden implementieren
Ein Delegat ist ein Verweistyp, der auf eine freigegebene Prozedur oder auf eine Instanzenprozedur eines Objekts verweist. Die Prozedur, auf die der Delegat verweist, kann durch eine Zuweisung geändert werden, und daher kann die `Delegate`\-Anweisung keine `Handles`\- oder `Implements`\-Klauseln unterstützen.  
  
 **Fehler\-ID:** BC30018  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die `Implements`\-Klausel aus der `Delegate`\-Anweisung.  
  
## Siehe auch  
 [NICHT IM BUILD: Delegaten und der AddressOf\-Operator](assetId:///7b2ed932-8598-4355-b2f7-5cedb23ee86f)   
 [Delegate Statement](../Topic/Delegate%20Statement.md)   
 [Handles](../Topic/Handles%20Clause%20\(Visual%20Basic\).md)   
 [Implements Statement](../Topic/Implements%20Statement.md)