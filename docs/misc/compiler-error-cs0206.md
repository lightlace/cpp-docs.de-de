---
title: "Compilerfehler CS0206"
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
  - "CS0206"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0206"
ms.assetid: d2f9838a-d8ae-4342-b8bd-fa5745619a26
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0206
Eine Eigenschaft oder ein Indexer kann nicht als out\- oder ref\-Parameter übergeben werden.  
  
 Es ist keine [Eigenschaft](../Topic/Properties%20\(C%23%20Programming%20Guide\).md) verfügbar, die als [ref](../Topic/ref%20\(C%23%20Reference\).md)\- oder [out](../Topic/out%20\(C%23%20Reference\).md)\-Parameter übergeben werden könnte. Weitere Informationen finden Sie unter [Übergeben von Parametern](../Topic/Passing%20Parameters%20\(C%23%20Programming%20Guide\).md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS0206 generiert:  
  
```  
// CS0206.cs public class MyClass { public static int P { get { return 0; } set { } } public static void MyMeth(ref int i) // public static void MyMeth(int i) { } public static void Main() { MyMeth(ref P);   // CS0206 // try the following line instead // MyMeth(P);   // CS0206 } }  
```