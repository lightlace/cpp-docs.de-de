---
title: "Compilerfehler CS0210"
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
  - "CS0210"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0210"
ms.assetid: 9f2ec1b8-6ca4-4147-b004-e3b43e7e8754
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0210
Sie müssen in einer fixed\- oder using\-Anweisungsdeklaration einen Initialisierer bereitstellen.  
  
 Müssen Sie die Variable in einer [fixed\-Anweisung](../Topic/fixed%20Statement%20\(C%23%20Reference\).md) deklarieren und initialisieren. Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../Topic/Unsafe%20Code%20and%20Pointers%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0210 generiert:  
  
```  
// CS0210a.cs // compile with: /unsafe class Point { public int x, y; } public class MyClass { unsafe public static void Main() { Point pt = new Point(); fixed (int i)    // CS0210 { } // try the following lines instead /* fixed (int* p = &pt.x) { } fixed (int* q = &pt.y) { } */ } }  
```  
  
 Im folgenden Beispiel wird auch CS0210 generiert, da die [using\-Anweisung](../Topic/using%20Statement%20\(C%23%20Reference\).md) keinen Initialisierer aufweist.  
  
```  
// CS0210b.cs using System.IO; class Test { static void Main() { using (StreamWriter w) // CS0210 // Try this line instead: // using (StreamWriter w = new StreamWriter("TestFile.txt")) { w.WriteLine("Hello there"); } } }  
```