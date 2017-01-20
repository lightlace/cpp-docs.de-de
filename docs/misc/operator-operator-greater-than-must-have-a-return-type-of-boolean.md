---
title: "Der &lt;Operator&gt;-Operator muss den R&#252;ckgabetyp &quot;Boolean&quot; haben."
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
  - "vbc33023"
  - "bc33023"
helpviewer_keywords: 
  - "BC33023"
ms.assetid: 18e066f4-d71e-4e38-b0bc-8af9145f6015
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Der &lt;Operator&gt;-Operator muss den R&#252;ckgabetyp &quot;Boolean&quot; haben.
Ein Vergleichs\- oder logischer Operator ist mit einem Rückgabetyp deklariert, der nicht der [Boolean Data Type](../Topic/Boolean%20Data%20Type%20\(Visual%20Basic\).md) ist.  
  
 Das Ergebnis eines Vergleichsoperators \(`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `IsFalse`, `IsTrue`, `Like`, `TypeOf`\) kann nur `True` oder `False` sein. Weitere Informationen finden Sie unter [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md).  
  
 Logische Operatoren \(`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`\) funktionieren ausschließlich im Definitionsbereich von booleschen Werten. Weitere Informationen finden Sie unter [Logical and Bitwise Operators in Visual Basic](../Topic/Logical%20and%20Bitwise%20Operators%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC33023  
  
### So beheben Sie diesen Fehler  
  
-   Ersetzen Sie den Rückgabetyp dieses Vergleichs\-oder logischen Operators durch `Boolean`.  
  
## Siehe auch  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)