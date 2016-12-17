---
title: "Der Zugriffsmodifizierer kann entweder auf &#39;Get&#39; oder Set&#39; angewendet werden, aber nicht auf beide."
ms.custom: na
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc31101"
  - "vbc31101"
helpviewer_keywords: 
  - "BC31101"
ms.assetid: c2a0580c-ff2f-4cc9-9113-6e540f906eec
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Der Zugriffsmodifizierer kann entweder auf &#39;Get&#39; oder Set&#39; angewendet werden, aber nicht auf beide.
Eine Eigenschaftendeklaration gibt Zugriffsebenen sowohl in der [Property Statement](../Topic/Property%20Statement.md), [Get Statement](../Topic/Get%20Statement.md) und der [Set Statement](../Topic/Set%20Statement%20\(Visual%20Basic\).md) an.  
  
 Sie können stets eine Zugriffsebene für die Eigenschaft angeben. Darüber hinaus können Sie eine andere Zugriffsebene für höchstens eine der Eigenschaftenprozeduren \(`Get` oder `Set`\) angeben, sofern diese restriktiver als die Zugriffsebene der Eigenschaft ist. Sie können keine Zugriffsebenen für beide Eigenschaftenprozeduren angeben.  
  
 **Fehler\-ID:** BC31101  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie den Zugriffsmodifizierer aus der `Get`\- oder `Set`\-Anweisung.  
  
## Siehe auch  
 [Eigenschaftenprozeduren](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)