---
title: "&#39;Group&#39; oder ID erwartet"
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
  - "vbc36707"
  - "bc36707"
helpviewer_keywords: 
  - "BC36707"
ms.assetid: 214e4aa3-d20f-41b3-902c-f1076d31b832
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Group&#39; oder ID erwartet
Der `Into`\-Teil einer `Group By`\- oder `Group Join`\-Klausel enthält das `Group`\-Schlüsselwort nicht. Sie müssen das `Group`\-Schlüsselwort in die `Into`\-Klausel einer `Group By`\- oder `Group Join`\-Klausel einschließen, um den für die gruppierten Ergebnisse zu verwendenden Variablennamen zu erkennen. Dabei kann es sich entweder um einen von Ihnen angegebenen Namen oder um das Schlüsselwort `Group` handeln.  
  
 **Fehler\-ID:** BC36707  
  
### So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass der `Into`\-Teil der `Group By`\- oder `Group Join`\-Klausel das `Group`\-Schlüsselwort enthält, wie im folgenden Beispiel gezeigt.  
  
    ```vb#  
    Dim orders = From order In orderList _ Order By order.OrderDate _ Group By OrderDate = order.OrderDate _ Into OrdersByDate = Group  
    ```  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [Group By\-Klausel](../Topic/Group%20By%20Clause%20\(Visual%20Basic\).md)   
 [Group Join Clause](../Topic/Group%20Join%20Clause%20\(Visual%20Basic\).md)