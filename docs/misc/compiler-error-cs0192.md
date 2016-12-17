---
title: "Compilerfehler CS0192"
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
  - "CS0192"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0192"
ms.assetid: d3fb6d18-dbf3-42c3-a280-afe55b97c2d1
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0192
An Felder des statischen schreibgeschützten Felds „name“ kann kein Verweis und keine Ausgabe übergeben werden \(Ausnahme: in einem statischen Konstruktor\).  
  
 Ein Feld \(Variable\), das mit dem [readonly](../Topic/readonly%20\(C%23%20Reference\).md)\-Schlüsselwort markiert ist, kann nur innerhalb eines Konstruktors an einen [ref](../Topic/ref%20\(C%23%20Reference\).md) oder [out](../Topic/out%20\(C%23%20Reference\).md)\-Parameter übergeben werden. Weitere Informationen finden Sie unter [Felder](../Topic/Fields%20\(C%23%20Programming%20Guide\).md).  
  
 CS0192 wird auch ausgegeben, wenn das `readonly`\-Feld [static](../Topic/static%20\(C%23%20Reference\).md) ist und der Konstruktor nicht als `static` markiert ist.  
  
## Beispiel  
 Im folgenden Beispiel wird CS0192 generiert:  
  
```  
// CS0192.cs class MyClass { public readonly int TestInt = 6; static void TestMethod(ref int testInt) { testInt = 0; } MyClass() { TestMethod(ref TestInt);   // OK } public void PassReadOnlyRef() { TestMethod(ref TestInt);   // CS0192 } public static void Main() { } }  
```