---
title: "Compilerfehler CS1947"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS1947"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1947"
ms.assetid: e2822fba-a176-4466-9cdc-63c44e22ebcb
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1947
Der Bereichsvariablen 'variablenname' kann nichts zugewiesen werden, sie ist schreibgeschützt.  
  
 Eine Bereichsvariable ist wie eine Iterationsvariable in einer `foreach`\-Anweisung. Ihr kann in einem Abfrageausdruck nichts zugewiesen werden.  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die Zuordnung zu der Bereichsvariablen.  
  
2.  Führen Sie ggf. mithilfe der `let`\-Klausel eine neue Bereichsvariable ein, und verwenden Sie diese zum Speichern des Werts.  
  
## Beispiel  
 Durch den folgenden Code wird der Fehler CS1947 ausgelöst:  
  
```  
// cs1947.cs using System.Linq; class Test { static void Main() { int[] array = new int[] { 1, 2, 3, 4, 5 }; var x = from i in array let k = i select i = 5; // CS1947 x.ToList(); } }  
```  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../Topic/LINQ%20Query%20Expressions%20\(C%23%20Programming%20Guide\).md)