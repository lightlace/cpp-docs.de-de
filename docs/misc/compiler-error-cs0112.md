---
title: "Compilerfehler CS0112"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0112"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0112"
ms.assetid: 6741c7c4-8553-4bbe-b950-4f908e8d9ba3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0112
Ein statischer Member "Funktion" kann nicht als "override", "virtual" oder "abstract" markiert werden.  
  
 Eine Methodendeklaration, die das `override`\-, **virtual**\- oder **abstract**\-Schlüsselwort verwendet, darf nicht auch das **static**\-Schlüsselwort verwenden.  
  
 Weitere Informationen finden Sie unter [Methoden](../Topic/Methods%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0112 generiert:  
  
```  
// CS0112.cs namespace MyNamespace { abstract public class MyClass { public abstract void Foo(); } public class MyClass2 : MyClass { override public static void Foo()   // CS0112, remove static keyword { } public static int Main() { return 0; } } }  
```