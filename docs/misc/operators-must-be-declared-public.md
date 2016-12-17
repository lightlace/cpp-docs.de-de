---
title: "Operatoren m&#252;ssen als &quot;Public&quot; deklariert werden."
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
  - "vbc33011"
  - "bc33011"
helpviewer_keywords: 
  - "BC33011"
ms.assetid: 67fc0dee-4ef5-4afc-a63a-f7d20bce7954
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Operatoren m&#252;ssen als &quot;Public&quot; deklariert werden.
[Operator Statement](../Topic/Operator%20Statement.md) enthält kein [Public](../Topic/Public%20\(Visual%20Basic\).md)\-Schlüsselwort.  
  
 Eine `Operator`\-Prozedur erfordert sowohl das `Public`\-Schlüsselwort als auch das [Shared](../Topic/Shared%20\(Visual%20Basic\).md)\-Schlüsselwort, und ein Konvertierungsoperator erfordert auch entweder das [Widening](../Topic/Widening%20\(Visual%20Basic\).md)\-Schlüsselwort oder das [Narrowing](../Topic/Narrowing%20\(Visual%20Basic\).md)\-Schlüsselwort.  
  
 **Fehler\-ID:** BC33011  
  
### So beheben Sie diesen Fehler  
  
-   Fügen Sie der `Operator`\-Anweisung das `Public`\-Schlüsselwort hinzu.  
  
## Siehe auch  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)