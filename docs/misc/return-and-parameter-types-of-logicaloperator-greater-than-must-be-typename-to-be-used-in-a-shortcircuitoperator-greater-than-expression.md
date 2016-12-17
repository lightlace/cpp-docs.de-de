---
title: "Die R&#252;ckgabe- und Parametertypen von &#39;&lt;logischeroperator&gt;&#39; m&#252;ssen &#39;&lt;typname&gt;&#39; sein, wenn sie in einem &lt;kurzschlussoperator&gt;-Ausdruck verwendet werden sollen"
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
  - "vbc33034"
  - "bc33034"
helpviewer_keywords: 
  - "BC33034"
ms.assetid: 94cd52dc-5d48-4673-b0b8-38a1954483c6
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "shoag"
manager: "wpickett"
---
# Die R&#252;ckgabe- und Parametertypen von &#39;&lt;logischeroperator&gt;&#39; m&#252;ssen &#39;&lt;typname&gt;&#39; sein, wenn sie in einem &lt;kurzschlussoperator&gt;-Ausdruck verwendet werden sollen
Ein `And`\-Operator oder ein `Or`\-Operator ist mit unpassenden Parametern oder Rückgabetypen für die Verwendung in einem [AndAlso Operator](../Topic/AndAlso%20Operator%20\(Visual%20Basic\).md) oder einem [OrElse Operator](../Topic/OrElse%20Operator%20\(Visual%20Basic\).md) deklariert.  
  
 Da Sie einen Kurzschlussoperator \(`AndAlso` oder `OrElse`\) nicht direkt definieren, müssen Sie die entsprechenden logischen und Bestimmungsoperatoren definieren. In der folgenden Tabelle sind die erforderlichen Operatoren zusammengestellt.  
  
|Kurzschlussoperator|Logischer Operator|Bestimmungsoperator|  
|-------------------------|------------------------|-------------------------|  
|`AndAlso`|[And Operator](../Topic/And%20Operator%20\(Visual%20Basic\).md)|[IsFalse Operator](../Topic/IsFalse%20Operator%20\(Visual%20Basic\).md)|  
|`OrElse`|[Or Operator](../Topic/Or%20Operator%20\(Visual%20Basic\).md)|[IsTrue Operator](../Topic/IsTrue%20Operator%20\(Visual%20Basic\).md)|  
  
 [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] verwendet diese logischen und Bestimmungsoperatoren dazu, die Kurzschlusslogik für `AndAlso` oder `OrElse` zu erstellen. Damit dies ordnungsgemäß funktioniert, müssen sowohl die Operanden als auch der Rückgabewert Ihrer `And`\- oder `Or`\-Definition den enthaltenden Typ haben, d. h., sie müssen den Typ der Klasse oder Struktur haben, in der Sie `And` oder `Or` definieren.  
  
 **Fehler\-ID:** BC33034  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie den Typ beider Operanden und den Rückgabewert in den Typ der Klasse oder Struktur, in der Sie den Operator definieren.  
  
     \- oder \-  
  
-   Verwenden Sie nicht den entsprechenden Kurzschlussoperator \(`AndAlso` oder `OrElse`\) mit Operanden vom Typ der Klasse oder Struktur, in der Sie diesen `And`\- oder `Or`\-Operator definieren.  
  
## Siehe auch  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Logical and Bitwise Operators in Visual Basic](../Topic/Logical%20and%20Bitwise%20Operators%20in%20Visual%20Basic.md)