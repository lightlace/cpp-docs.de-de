---
title: "Compilerfehler CS0631"
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
  - "CS0631"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0631"
ms.assetid: 5ae06b13-7874-4d0d-b256-7d8b33396156
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0631
"ref" und "out" sind in diesem Kontext nicht gültig.  
  
 Die Deklaration für einen [Indexer](../Topic/Indexers%20\(C%23%20Programming%20Guide\).md) darf nicht von den Parametern [ref](../Topic/ref%20\(C%23%20Reference\).md) und [out](../Topic/out%20\(C%23%20Reference\).md) Gebrauch machen.  
  
## Beispiel  
 Im folgenden Beispiel wird CS0631 generiert:  
  
```  
// CS0631.cs public class MyClass { public int this[ref int i]   // CS0631 // try the following line instead // public int this[int i] { get { return 0; } } } public class MyClass2 { public static void Main() { } }  
```