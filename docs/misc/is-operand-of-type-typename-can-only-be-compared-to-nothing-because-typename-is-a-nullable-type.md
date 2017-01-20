---
title: "Ein &quot;Is&quot;-Operand vom Typ &quot;Typname&quot; kann nur mit &quot;Nothing&quot; verglichen werden, da &quot;Typname&quot; ein Typ ist, der NULL-Werte zul&#228;sst"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc32127"
  - "bc32127"
helpviewer_keywords: 
  - "BC32127"
ms.assetid: 68b745b5-8605-4bf3-a6ec-69e67b3cff2d
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "shoag"
manager: "wpickett"
---
# Ein &quot;Is&quot;-Operand vom Typ &quot;Typname&quot; kann nur mit &quot;Nothing&quot; verglichen werden, da &quot;Typname&quot; ein Typ ist, der NULL-Werte zul&#228;sst
Eine Variable, die als auf NULL festlegbar deklariert wurde, wurde mithilfe des `Is`\-Operators mit einem anderen Ausdruck als `Nothing` verglichen.  
  
 **Fehler\-ID:** BC32127  
  
### So beheben Sie diesen Fehler  
  
1.  Um einen Typ, der NULL zulässt, mithilfe des `Is`\-Operators mit einem anderen Ausdruck als `Nothing` zu vergleichen, rufen Sie die `GetType`\-Methode für den Typ, der NULL zulässt, auf und vergleichen das Ergebnis mit dem Ausdruck, wie im folgenden Beispiel gezeigt.  
  
    ```vb#  
    Dim number? As Integer = 5 If number IsNot Nothing Then If number.GetType() Is Type.GetType("System.Int32") Then End If End If  
    ```  
  
## Siehe auch  
 [Nullable Value Types](../Topic/Nullable%20Value%20Types%20\(Visual%20Basic\).md)   
 [Is Operator](../Topic/Is%20Operator%20\(Visual%20Basic\).md)