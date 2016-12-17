---
title: "Keine zugreifbare &lt;Name der generischen Prozedur&gt; akzeptiert diese Anzahl von Typargumenten."
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
  - "bc32118"
  - "vbc32118"
helpviewer_keywords: 
  - "BC32118"
ms.assetid: 4ee942ba-0fa1-4ec1-9c2c-a0c0dc3f1b17
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "shoag"
manager: "wpickett"
---
# Keine zugreifbare &lt;Name der generischen Prozedur&gt; akzeptiert diese Anzahl von Typargumenten.
Eine Anweisung ruft eine generische Prozedur auf, die mehrere überladene Versionen aufweist, aber keine der überladenen Versionen definiert die gleiche Anzahl von Typparametern, wie die Anzahl der im Aufruf angegebenen Typargumente.  
  
 Wenn nur eine generische Version vorhanden ist, rufen Sie diese ohne Typargumente auf, und der Compiler kann einen *Typrückschluss* versuchen. Weitere Informationen finden Sie unter „Typrückschluss“ in [Generic Procedures in Visual Basic](../Topic/Generic%20Procedures%20in%20Visual%20Basic.md). Wenn jedoch mehrere generische Versionen vorhanden sind, kann der Compiler nur dann eine Auswahl treffen, wenn Sie Typargumente angeben. Wenn Sie ein Typargument angeben, müssen Sie ein Typargument für jeden Typparameter angeben, der von einer der überladenen Versionen definiert wird.  
  
 **Fehler\-ID:** BC32118  
  
### So beheben Sie diesen Fehler  
  
-   Entscheiden Sie, welche überladene Version Sie aufrufen möchten, und geben Sie dann die entsprechende Anzahl von Typargumenten an.  
  
## Siehe auch  
 [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md)   
 [Procedure Overloading](../Topic/Procedure%20Overloading%20\(Visual%20Basic\).md)   
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Generic Procedures in Visual Basic](../Topic/Generic%20Procedures%20in%20Visual%20Basic.md)