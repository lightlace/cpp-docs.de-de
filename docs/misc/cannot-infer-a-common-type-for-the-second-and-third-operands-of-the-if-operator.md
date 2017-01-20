---
title: "Es kann kein gemeinsamer Typ f&#252;r den zweiten und dritten Operanden des If-Operators abgeleitet werden"
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
  - "vbc33106"
  - "bc33106"
helpviewer_keywords: 
  - "BC33106"
ms.assetid: 793eed88-a9f9-43e3-b657-c16795ecbbcc
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# Es kann kein gemeinsamer Typ f&#252;r den zweiten und dritten Operanden des If-Operators abgeleitet werden
Es kann kein gemeinsamer Typ für den zweiten und dritten Operanden des If\-Operators abgeleitet werden. Für einen muss eine Widening\-Konvertierung in den anderen durchgeführt werden.  
  
 Wenn der `If`\-Operator mit drei Argumenten aufgerufen wird, muss zwischen dem zweiten und dritten Argument eine Widening\-Konvertierung durchgeführt werden. Da beispielsweise keine Widening\-Konvertierung in keine Richtung zwischen `Integer` und `String` durchgeführt wird, verursacht folgender Code diesen Fehler.  
  
```vb#  
Dim divisor = 3  
' Not valid.  
' Console.WriteLine(If(divisor <> 0, number \ divisor, "Division by zero"))  
```  
  
 **Fehler\-ID:** BC33106  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie eine explizite Konvertierung für einen der Operanden an, wenn dies in Ihrem Code möglich ist.  
  
-   Verwenden Sie eine andere Bedingungskonstruktion, z. B. eine `If...Then...Else`\-Anweisung.  
  
## Siehe auch  
 [If Operator](../Topic/If%20Operator%20\(Visual%20Basic\).md)   
 [If...Then...Else Statement](../Topic/If...Then...Else%20Statement%20\(Visual%20Basic\).md)   
 [Widening and Narrowing Conversions](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md)