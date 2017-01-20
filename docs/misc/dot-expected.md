---
title: "&quot;.&quot; erwartet"
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
  - "bc30287"
  - "vbc30287"
helpviewer_keywords: 
  - "BC30287"
ms.assetid: 7d7b4934-b521-4ed3-b054-aeb71f8daacf
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;.&quot; erwartet
Der Code enthält eine `Handles`\-Klausel mit einem Ausrufezeichen \(`!`\).  
  
 **Fehler\-ID:** BC30287  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn die `Handles`\-Klausel auf ein Ereignis in einem Objekt verweist, verwenden Sie einen Punkt \(`.`\), um das Objekt von dem Ereignis zu trennen.  
  
     In diesem Beispiel wird das `Click`\-Ereignis aus dem `Button1`\-Objekt behandelt.  
  
     [!CODE [VbVbalrEventError#21](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#21)]  
  
## Siehe auch  
 [Handles](../Topic/Handles%20Clause%20\(Visual%20Basic\).md)