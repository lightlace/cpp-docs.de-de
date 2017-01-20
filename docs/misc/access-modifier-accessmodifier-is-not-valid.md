---
title: "Der Zugriffsmodifizierer &#39;&lt;zugriffsmodifizierer&gt;&#39; ist ung&#252;ltig"
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
  - "bc31100"
  - "vbc31100"
helpviewer_keywords: 
  - "BC31100"
ms.assetid: 1cd71acc-0b54-4f64-8d61-75b272d293cb
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Der Zugriffsmodifizierer &#39;&lt;zugriffsmodifizierer&gt;&#39; ist ung&#252;ltig
Eine [Get Statement](../Topic/Get%20Statement.md)\- oder [Set Statement](../Topic/Set%20Statement%20\(Visual%20Basic\).md)\-Anweisung gibt eine Zugriffsebene an, die weniger einschränkend als die für die enthaltende Eigenschaft festgelegte Zugriffsebene ist.  
  
 Sie können stets eine Zugriffsebene für die Eigenschaft angeben. Darüber hinaus können Sie eine andere Zugriffsebene für höchstens eine der Eigenschaftenprozeduren \(`Get` oder `Set`\) angeben, sofern diese restriktiver als die Zugriffsebene der Eigenschaft ist. Wenn die Eigenschaft beispielsweise `Friend` ist, können Sie `Private` für eine Eigenschaftenprozedur festlegen, nicht jedoch `Public`. Sie können keine Zugriffsebenen für beide Eigenschaftenprozeduren angeben.  
  
 **Fehler\-ID:** BC31100  
  
### So beheben Sie diesen Fehler  
  
-   Legen Sie die Zugriffsebene für die Eigenschaftenprozedur stärker einschränkend als für die Eigenschaft fest, oder entfernen Sie den Zugriffsmodifizierer ganz.  
  
-   Deklarieren Sie die weniger restriktive Zugriffsebene in der [Property Statement](../Topic/Property%20Statement.md), und deklarieren Sie die stärker einschränkende Zugriffsebene in einer der Eigenschaftenprozeduren.  
  
## Siehe auch  
 [Eigenschaftenprozeduren](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)