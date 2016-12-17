---
title: "&#39;IsNot&#39; erfordert Operanden mit Referenztypen. Dieser Operand hat jedoch den Werttyp &#39;&lt;Typname&gt;&#39;."
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
  - "bc31419"
  - "vbc31419"
helpviewer_keywords: 
  - "BC31419"
ms.assetid: c44d2936-8c07-443a-b320-ac2bfbc1e9ec
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;IsNot&#39; erfordert Operanden mit Referenztypen. Dieser Operand hat jedoch den Werttyp &#39;&lt;Typname&gt;&#39;.
Ein Ausdruck verwendet den [IsNot Operator](../Topic/IsNot%20Operator%20\(Visual%20Basic\).md) mit mindestens einem Werttypoperanden.  
  
 Der `IsNot`\-Operator bestimmt, ob zwei Objektverweise auf unterschiedliche Objekte verweisen. Er vergleicht die Zeigerwerte von Verweistypen und ist für Werttypen ohne Bedeutung.  
  
 **Fehler\-ID:** BC31419  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie die Werte zweier Werttypen vergleichen möchten, verwenden Sie den Vergleichsoperator `=` oder `<>`.  
  
-   Wenn Sie die Zeiger zweier Verweistypen vergleichen möchten, achten Sie darauf, dass Sie für beide Operanden Objektverweise verwenden. Sie können Verweisvariablen oder Elemente wie das [Me](assetId:///a65973c7-cf06-4547-9b25-9fba885525c2)\-Schlüsselwort verwenden, die sich wie Verweisvariablen verhalten.  
  
## Siehe auch  
 [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)   
 [How to: Test Whether Two Objects Are the Same](../Topic/How%20to:%20Test%20Whether%20Two%20Objects%20Are%20the%20Same%20\(Visual%20Basic\).md)