---
title: "Nur Konvertierungsoperatoren k&#246;nnen als &#39;&lt;schl&#252;sselwort&gt;&#39; deklariert werden."
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
  - "bc33019"
  - "vbc33019"
helpviewer_keywords: 
  - "BC33019"
ms.assetid: 946266fe-a909-41b1-aad4-f85dc8050b88
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Nur Konvertierungsoperatoren k&#246;nnen als &#39;&lt;schl&#252;sselwort&gt;&#39; deklariert werden.
Ein [Operator Statement](../Topic/Operator%20Statement.md) gibt [Widening](../Topic/Widening%20\(Visual%20Basic\).md) oder [Narrowing](../Topic/Narrowing%20\(Visual%20Basic\).md) an, obwohl es sich bei dem Operator nicht um einen Konversionsoperator handelt.  
  
 Jeder Operator muss sowohl als [Public](../Topic/Public%20\(Visual%20Basic\).md) als auch als [Shared](../Topic/Shared%20\(Visual%20Basic\).md) deklariert werden. Jedoch können nur Konversionsoperatoren als [Widening](../Topic/Widening%20\(Visual%20Basic\).md) oder [Narrowing](../Topic/Narrowing%20\(Visual%20Basic\).md) deklariert werden, nicht jedoch beides.  
  
 Eine Operatordefinition kann optional die Schlüsselwörter [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md) und [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md) enthalten. Keine anderen Schlüsselwörter sind in einem [Operator Statement](../Topic/Operator%20Statement.md) zulässig.  
  
 **Fehler\-ID:** BC33019  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie das `Widening`\- oder `Narrowing`\-Schlüsselwort aus der Operatordefinition. Diese gelten nicht, da keine Typkonvertierung stattfindet.  
  
## Siehe auch  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Type Conversions in Visual Basic](../Topic/Type%20Conversions%20in%20Visual%20Basic.md)