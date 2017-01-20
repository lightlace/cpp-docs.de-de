---
title: "&quot;On&quot; erwartet."
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
  - "bc36618"
  - "vbc36618"
helpviewer_keywords: 
  - "BC36618"
ms.assetid: 7cb1b205-c4c3-4485-ae3f-8942425692ff
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;On&quot; erwartet.
Eine `Join`\- oder `Group Join`\-Klausel wurde ohne den `On`\-Operator angegeben. Der `On`\-Operator wird verwendet, um das Schlüsselfeld der Bereichsvariablen für jede Auflistung zu definieren. Schlüsselfelder werden verwendet, um Elemente aus jeder Auflistung abzugleichen.  
  
 **Fehler\-ID:** BC36618  
  
### So beheben Sie diesen Fehler  
  
1.  Fügen Sie der `Join`\- oder `Group Join`\-Klausel den `On`\-Operator und Schlüsselfelder hinzu. Beachten Sie folgendes Beispiel:  
  
    ```vb#  
    Dim petOwnersJoin = From pers In people _ Join pet In pets _ On pet.Owner Equals pers _ Select pers.FirstName, PetName = pet.Name  
    ```  
  
## Siehe auch  
 [How to: Combine Data with Joins](../Topic/How%20to:%20Combine%20Data%20with%20LINQ%20by%20Using%20Joins%20\(Visual%20Basic\).md)   
 [Join Clause](../Topic/Join%20Clause%20\(Visual%20Basic\).md)   
 [Group Join Clause](../Topic/Group%20Join%20Clause%20\(Visual%20Basic\).md)   
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)