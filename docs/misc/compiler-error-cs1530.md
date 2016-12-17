---
title: "Compilerfehler CS1530"
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
  - "CS1530"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1530"
ms.assetid: 3844b5ef-e0ec-42df-9267-72689020f128
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1530
Das Schlüsselwort 'new' ist für Elemente, die in einem Namespace definiert sind, nicht zulässig.  
  
 Das Schlüsselwort [new](../Topic/new%20\(C%23%20Reference\).md) muss für Konstrukte in einem [Namespace](../Topic/namespace%20\(C%23%20Reference\).md) nicht angegeben werden.  
  
 Im folgenden Beispiel wird CS1530 generiert:  
  
```  
// CS1530.cs namespace a { new class i   // CS1530 { } // try the following instead class ii { public static void Main() { } } }  
```