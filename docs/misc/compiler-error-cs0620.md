---
title: "Compilerfehler CS0620"
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
  - "CS0620"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0620"
ms.assetid: cadd7156-0c3c-460b-844b-c9bbfb8f62df
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0620
Indexer können keinen leeren Typ haben.  
  
 Der Rückgabetyp eines [Indexers](../Topic/Indexers%20\(C%23%20Programming%20Guide\).md) kann nicht `void` sein. Ein Indexer muss einen Wert zurückgeben.  
  
 Im folgenden Beispiel wird CS0620 generiert:  
  
```  
// CS0620.cs class MyClass { public static void Main() { MyClass test = new MyClass(); System.Console.WriteLine(test[2]); } void this [int intI]   // CS0620, return type cannot be void { get { // will need to return some value } } }  
```  
  
## Siehe auch  
 [void](../Topic/void%20\(C%23%20Reference\).md)