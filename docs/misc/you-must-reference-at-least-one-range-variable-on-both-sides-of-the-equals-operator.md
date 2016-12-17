---
title: "Verweisen Sie auf beiden Seiten des Equals-Operators auf mindestens eine Bereichsvariable."
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
  - "vbc36622"
  - "bc36622"
helpviewer_keywords: 
  - "BC36622"
ms.assetid: 8d301227-131d-4977-b3ff-1fc4e427f8fa
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "shoag"
manager: "wpickett"
---
# Verweisen Sie auf beiden Seiten des Equals-Operators auf mindestens eine Bereichsvariable.
Verweisen Sie auf beiden Seiten des Equals\-Operators auf mindestens eine Bereichsvariable. Die Bereichsvariablen "\<Variable\(n\)\>" müssen auf einer Seite des Equals\-Operators und die Bereichsvariablen "\<Variable\(n\)\>" müssen auf der anderen Seite verwendet werden.  
  
 Bereichsvariablen, die für Auflistungen identifiziert werden, die in einer LINQ\-Abfrage verknüpft werden sollen, müssen sich abhängig von der Auflistung, für die sie identifiziert wurden, auf gegenüberliegenden Seiten des `Equals`\-Operators befinden. Dies bedeutet, dass sich Bereichsvariablen, die für eine der zu verknüpfenden Auflistungen identifiziert werden, und Bereichsvariablen für die andere zu verknüpfende Auflistung auf gegenüberliegenden Seiten des `Equals`\-Operators befinden müssen. Bereichsvariablen aus getrennten Auflistungen dürfen nicht auf der derselben Seite des `Equals`\-Operators stehen.  
  
 Auf jeder Seite des `Equals`\-Operators muss auf mindestens eine Variable aus jeder zu verknüpfenden Auflistung verwiesen werden.  
  
 **Fehler\-ID:** BC36622  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)   
 [Join Clause](../Topic/Join%20Clause%20\(Visual%20Basic\).md)   
 [Group Join Clause](../Topic/Group%20Join%20Clause%20\(Visual%20Basic\).md)   
 [From Clause](../Topic/From%20Clause%20\(Visual%20Basic\).md)   
 [Select Clause](../Topic/Select%20Clause%20\(Visual%20Basic\).md)