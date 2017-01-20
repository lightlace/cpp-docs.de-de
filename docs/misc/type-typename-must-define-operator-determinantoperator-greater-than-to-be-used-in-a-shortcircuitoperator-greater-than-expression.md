---
title: "Der Typ &quot;&lt;Typname&gt;&quot; muss den &lt;Bestimmungsoperator&gt;-Operator definieren, damit er in einem &lt;Kurzschlussoperator&gt;-Ausdruck verwendet werden kann."
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc33035"
  - "vbc33035"
helpviewer_keywords: 
  - "BC33035"
ms.assetid: 50a0a39f-63cd-4100-aea9-91b5b6ab5bbf
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Der Typ &quot;&lt;Typname&gt;&quot; muss den &lt;Bestimmungsoperator&gt;-Operator definieren, damit er in einem &lt;Kurzschlussoperator&gt;-Ausdruck verwendet werden kann.
In einem [AndAlso Operator](../Topic/AndAlso%20Operator%20\(Visual%20Basic\).md) oder [OrElse Operator](../Topic/OrElse%20Operator%20\(Visual%20Basic\).md) werden Operanden eines Klassen\- oder Strukturtyps verwendet, obwohl in dieser Klasse oder Struktur ein erforderlicher Operator nicht definiert ist.  
  
 Da Sie keinen Kurzschlussoperator \(`AndAlso` oder `OrElse`\) direkt definieren, müssen Sie die entsprechenden logischen und Bestimmungsoperatoren definieren. In der folgenden Tabelle sind die erforderlichen Operatoren zusammengestellt.  
  
|Kurzschlussoperator|Logischer Operator|Bestimmungsoperator|  
|-------------------------|------------------------|-------------------------|  
|`AndAlso`|[And Operator](../Topic/And%20Operator%20\(Visual%20Basic\).md)|[IsFalse Operator](../Topic/IsFalse%20Operator%20\(Visual%20Basic\).md)|  
|`OrElse`|[Or Operator](../Topic/Or%20Operator%20\(Visual%20Basic\).md)|[IsTrue Operator](../Topic/IsTrue%20Operator%20\(Visual%20Basic\).md)|  
  
 [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] verwendet diese logischen und Bestimmungsoperatoren dazu, die Kurzschlusslogik für `AndAlso` oder `OrElse` zu erstellen. Damit dies ordnungsgemäß funktioniert, müssen sowohl die Operanden als auch der Rückgabewert Ihrer `And`\- oder `Or`\-Definition den enthaltenden Typ haben, d. h., sie müssen den Typ der Klasse oder Struktur haben, in der Sie `And` oder `Or` definieren.  
  
 **Fehler\-ID:** BC33035  
  
### So beheben Sie diesen Fehler  
  
-   Definieren Sie den `And`\- und den `IsFalse`\-Operator oder den `Or`\- und den `IsTrue`\-Operatoren in der Klasse oder Struktur, die für den Operandentyp des `AndAlso`\- oder `OrElse`\-Operators verwendet wird. Achten Sie darauf, dass die Operanden für `And` oder `Or` den Typ der Klasse oder Struktur haben, in der Sie die Operanden definieren.  
  
## Siehe auch  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Logical and Bitwise Operators in Visual Basic](../Topic/Logical%20and%20Bitwise%20Operators%20in%20Visual%20Basic.md)