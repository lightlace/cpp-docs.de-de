---
title: "Implements-Anweisungen m&#252;ssen allen Inherits-Anweisungen folgen und allen Deklarationen in einer Klasse voranstehen."
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
  - "bc31053"
  - "vbc31053"
helpviewer_keywords: 
  - "BC31053"
ms.assetid: 8036a1a1-7e31-4c49-b74b-01601a548f3e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Implements-Anweisungen m&#252;ssen allen Inherits-Anweisungen folgen und allen Deklarationen in einer Klasse voranstehen.
Eine `Implements`\-Anweisung wurde an einer ungültigen Stelle gefunden.  
  
 **Fehler\-ID:** BC31053  
  
### So beheben Sie diesen Fehler  
  
-   Ordnen Sie `Implements`\-Anweisungen unmittelbar nach `Inherits`\-Anweisungen, aber noch vor Deklarationen an. Zum Beispiel:  
  
    ```  
    Class Derived Inherits Base Implements One Sub SubOne() Implements One.Method1 ' Add code to implement the method. End Sub End Class  
    ```  
  
## Siehe auch  
 [Interfaces](../Topic/Interfaces%20\(Visual%20Basic\).md)   
 [Implements](../Topic/Implements%20Clause%20\(Visual%20Basic\).md)