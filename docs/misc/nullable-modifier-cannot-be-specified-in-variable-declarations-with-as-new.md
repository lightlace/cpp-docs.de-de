---
title: "In Variablendeklarationen mit &quot;As New&quot; darf kein Modifizierer, der NULL-Werte zul&#228;sst, angegeben werden."
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
  - "bc33109"
  - "vbc33109"
helpviewer_keywords: 
  - "BC33109"
ms.assetid: 135def20-3535-4239-bffb-43208d1b3f63
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# In Variablendeklarationen mit &quot;As New&quot; darf kein Modifizierer, der NULL-Werte zul&#228;sst, angegeben werden.
Der Typmodifizierer \(?\), der NULL\-Werte zulässt, ist in einer Variablendeklaration enthalten, in der `As New` angegeben wurde. Dieser Fehler wird beispielsweise durch den folgenden Code verursacht.  
  
```vb#  
Dim num? As New ExampleStructure  
```  
  
 **Fehler\-ID:** BC33109  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie das `New`\-Schlüsselwort aus der Variablendeklaration, die NULL\-Werte zulässt, wie im folgenden Beispiel gezeigt:  
  
    ```vb#  
    Dim num? As ExampleStructure  
    ```  
  
## Siehe auch  
 [Nullable Value Types](../Topic/Nullable%20Value%20Types%20\(Visual%20Basic\).md)