---
title: "Der Typ von &quot;&lt;Variablenname&gt;&quot; kann nicht von einem Ausdruck abgeleitet werden, der &quot;&lt;Variablenname&gt;&quot; enth&#228;lt."
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
  - "vbc30980"
  - "bc30980"
helpviewer_keywords: 
  - "BC30980"
ms.assetid: 43a5d008-5362-481b-845b-b9bb00a61a83
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "shoag"
manager: "wpickett"
---
# Der Typ von &quot;&lt;Variablenname&gt;&quot; kann nicht von einem Ausdruck abgeleitet werden, der &quot;&lt;Variablenname&gt;&quot; enth&#228;lt.
Der Compiler kann den Datentyp einer Variablen nicht ableiten, wenn die Variable zum Erstellen des Anfangswerts in der Deklaration verwendet wird.  
  
 Wenn die `Option Infer` beispielsweise auf `On` festgelegt ist, können die folgenden Beispiele nicht kompiliert werden:  
  
-   Deklarationen  
  
    ```  
    ' Does not compile with Option Infer on. Dim m = m Dim d = someFunction(d)  
    ```  
  
-   `For` Loop  
  
    ```  
    ' Does not compile with Option Infer on. For j = 1 To j Next  
    ```  
  
-   `For Each` Loop  
  
    ```  
    ' Does not compile with Option Infer on. For Each customer In customer.Orders Next  
    ```  
  
 **Fehler\-ID:** BC30980  
  
### So beheben Sie diesen Fehler  
  
-   Wenn die beiden Variablen auf verschiedene Werte verweisen sollen, ändern Sie den Namen der zu deklarierenden Variablen.  
  
-   Verwenden Sie im Anfangswert auf der rechten Seite der Zuweisung statt des Variablennamens einen Literalwert.  
  
-   Verwenden Sie eine `As`\-Klausel, um den Typ der zu deklarierenden Variablen anzugeben.  
  
## Siehe auch  
 [Dim Statement](../Topic/Dim%20Statement%20\(Visual%20Basic\).md)   
 [For Each...Next\-Anweisung](../Topic/For%20Each...Next%20Statement%20\(Visual%20Basic\).md)   
 [For...Next\-Anweisung](../Topic/For...Next%20Statement%20\(Visual%20Basic\).md)   
 [Local Type Inference](../Topic/Local%20Type%20Inference%20\(Visual%20Basic\).md)   
 [Option Infer Statement](../Topic/Option%20Infer%20Statement.md)