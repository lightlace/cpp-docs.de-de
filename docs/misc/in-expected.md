---
title: "&#39;In&#39; erwartet."
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
  - "bc36607"
  - "vbc36607"
helpviewer_keywords: 
  - "BC36607"
ms.assetid: f390bca5-12fe-4fe1-bd86-7f8ab66dfbd8
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;In&#39; erwartet.
Eine `From`\- oder `Aggregate`\-Klausel wurde ohne den `In`\-Operator angegeben. Sie verwenden die `In`\-Operator, um die abzufragende Auflistung zu identifizieren.  
  
 **Fehler\-ID:** BC36607  
  
### So beheben Sie diesen Fehler  
  
1.  Fügen Sie der `From`\- oder `Aggregate`\-Klausel den `In`\-Operator und Schlüsselfelder hinzu. Im Folgenden finden Sie ein Beispiel dazu:  
  
    ```vb#  
    Dim names = From pers In people Select pers.FirstName, pers.LastName  
    ```  
  
## Siehe auch  
 [From Clause](../Topic/From%20Clause%20\(Visual%20Basic\).md)   
 [Aggregate Clause](../Topic/Aggregate%20Clause%20\(Visual%20Basic\).md)   
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)