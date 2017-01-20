---
title: "Eigenschaftenaccessoren k&#246;nnen nicht als &lt;Schl&#252;sselwort&gt; deklariert werden."
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
  - "vbc31099"
  - "bc31099"
helpviewer_keywords: 
  - "BC31099"
ms.assetid: d6f3b989-39b9-4c47-995a-bd83ec03d7b8
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Eigenschaftenaccessoren k&#246;nnen nicht als &lt;Schl&#252;sselwort&gt; deklariert werden.
Eine `Get` oder `Set`\-Prozedurdeklaration enthält ein Schlüsselwort, das in einer Eigenschaftenprozedur nicht gültig ist.  
  
 Für [Get Statement](../Topic/Get%20Statement.md) und [Set Statement](../Topic/Set%20Statement%20\(Visual%20Basic\).md) ist nur ein Zugriffsmodifizierer zulässig \(`Public`, `Protected`, `Friend`, `Protected Friend`, `Private`\).  
  
 **Fehler\-ID:** BC31099  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das ungültige Schlüsselwort aus der `Get`\- oder `Set`\-Anweisung.  
  
## Siehe auch  
 [Eigenschaftenprozeduren](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)