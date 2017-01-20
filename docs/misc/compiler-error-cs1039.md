---
title: "Compilerfehler CS1039"
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
  - "CS1039"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1039"
ms.assetid: 266e9f7f-fe17-445a-aefd-6b7795167d68
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1039
Nicht beendetes Zeichenfolgenliteral.  
  
 Der Compiler hat ein [string](../Topic/string%20\(C%23%20Reference\).md)\-Literal in einem ungültigen Format erkannt.  
  
## Beispiel  
 Im folgenden Beispiel wird CS1039 generiert: Fügen Sie das abschließende Anführungszeichen hinzu, um den Fehler zu beheben.  
  
```  
// CS1039.cs public class MyClass { public static void Main() { string b = @"hello, world;   // CS1039 } }  
```