---
title: "&#39;Equals&#39; erwartet"
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
  - "vbc36619"
  - "bc36619"
helpviewer_keywords: 
  - "BC36619"
ms.assetid: 1fd8c0dc-0e87-47b7-ab30-498809cca033
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Equals&#39; erwartet
Eine `Join`\- oder `Group Join`\-Klausel wurde ohne den `Equals`\-Operator angegeben. Sie verwenden den `Equals`\-Operator zum Identifizieren der `Boolean`\-Operation, um Schlüsselfelder auf übereinstimmende Elemente zu testen.  
  
 **Fehler\-ID:** BC36619  
  
### So beheben Sie diesen Fehler  
  
1.  Fügen Sie der `Join`\- oder `Group Join`\-Klausel den `Equals`\-Operator und Schlüsselfelder hinzu. Zum Beispiel:  
  
    ```vb#  
    Dim petOwnersGrouped = From pers In people _ Group Join pet In pets _ On pers Equals pet.Owner _ Into PetList = Group _ Select pers.FirstName, pers.LastName, _ PetList  
    ```  
  
## Siehe auch  
 [How to: Combine Data with Joins](../Topic/How%20to:%20Combine%20Data%20with%20LINQ%20by%20Using%20Joins%20\(Visual%20Basic\).md)   
 [Join Clause](../Topic/Join%20Clause%20\(Visual%20Basic\).md)   
 [Group Join Clause](../Topic/Group%20Join%20Clause%20\(Visual%20Basic\).md)   
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)