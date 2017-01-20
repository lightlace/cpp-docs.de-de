---
title: "Compilerfehler CS1949"
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
  - "CS1949"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1949"
ms.assetid: 959f553e-ac3d-43a1-b0a0-11e270f2ad64
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1949
Das kontextbezogene Schlüsselwort 'var' darf nicht in der Deklaration einer Bereichsvariablen verwendet werden.  
  
 Eine Bereichsvariable wird implizit vom Compiler typisiert. Es ist nicht erforderlich, [var](../Topic/var%20\(C%23%20Reference\).md) für eine Bereichsvariable zu verwenden.  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie das Schlüsselwort `var`  vor der Bereichsvariablen.  
  
## Beispiel  
 Im folgenden Beispiel wird CS1949 generiert:  
  
```  
// cs1949.cs using System; using System.Linq; class Test { static void Main() { var x = from var i in Enumerable.Range(1, 100) // CS1949 select i; } }  
```  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../Topic/LINQ%20Query%20Expressions%20\(C%23%20Programming%20Guide\).md)   
 [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)