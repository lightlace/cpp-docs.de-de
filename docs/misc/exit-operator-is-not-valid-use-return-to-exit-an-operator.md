---
title: "&quot;Exit Operator&quot; ist nicht g&#252;ltig. Verwenden Sie &quot;Return&quot;, um einen Operator zu beenden."
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
  - "bc33008"
  - "vbc33008"
helpviewer_keywords: 
  - "BC33008"
ms.assetid: 8c44456b-8fd2-4168-ad8c-b6da129242ba
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Exit Operator&quot; ist nicht g&#252;ltig. Verwenden Sie &quot;Return&quot;, um einen Operator zu beenden.
Eine `Exit Operator`\-Anweisung ist in einer `Operator`\-Prozedur enthalten.  
  
 Für die Rückgabe von einer `Operator`\-Prozedur müssen Sie eine [Return Statement](../Topic/Return%20Statement%20\(Visual%20Basic\).md) verwenden. Die [Exit Statement](../Topic/Exit%20Statement%20\(Visual%20Basic\).md) akzeptiert das `Operator`\-Schlüsselwort nicht, und die `End Operator`\-Anweisung gibt die Steuerung nicht an den aufrufenden Code zurück.  
  
 **Fehler\-ID:** BC33008  
  
### So beheben Sie diesen Fehler  
  
-   Ersetzen Sie die `Exit Operator`\-Anweisung durch eine `Return`\-Anweisung.  
  
## Siehe auch  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)