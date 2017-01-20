---
title: "Compilerwarnung (Stufe 4) CS0628"
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
  - "CS0628"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0628"
ms.assetid: a54cfad8-27c9-4abb-8c83-982615489a10
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerwarnung (Stufe 4) CS0628
„member“: Ein neuer geschützter Member wurde in einer versiegelten Klasse deklariert.  
  
 Eine [versiegelte](../Topic/sealed%20\(C%23%20Reference\).md) Klasse kann keinen [geschützten](../Topic/protected%20\(C%23%20Reference\).md) Member einführen, da keine andere Klasse von der `sealed`\-Klasse erben und den `protected`\-Member verwenden kann.  
  
 Im folgenden Beispiel wird CS0628 generiert:  
  
```  
// CS0628.cs // compile with: /W:4 sealed class C { protected int i;   // CS0628 } class MyClass { public static void Main() { } }  
```