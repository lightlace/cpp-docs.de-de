---
title: "Compilerfehler CS0215"
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
  - "CS0215"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0215"
ms.assetid: 2060440d-be22-4c10-8b26-43b08b615447
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0215
Der Rückgabetyp des True\- oder False\-Operators muss boolesch sein.  
  
 Benutzerdefinierte [true](../Topic/true%20\(C%23%20Reference\).md)\- und [false](../Topic/false%20\(C%23%20Reference\).md)\-Operatoren müssen den Rückgabetyp [bool](../Topic/bool%20\(C%23%20Reference\).md) aufweisen. Weitere Informationen finden Sie unter [Überladbare Operatoren](../Topic/Overloadable%20Operators%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0215 generiert:  
  
```  
// CS0215.cs class MyClass { public static int operator true (MyClass MyInt)   // CS0215 // try the following line instead // public static bool operator true (MyClass MyInt) { return true; } public static int operator false (MyClass MyInt)   // CS0215 // try the following line instead // public static bool operator false (MyClass MyInt) { return true; } public static void Main() { } }  
```