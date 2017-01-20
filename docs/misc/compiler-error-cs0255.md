---
title: "Compilerfehler CS0255"
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
  - "CS0255"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0255"
ms.assetid: b45f5d5a-1923-4fe1-a858-e5ef5590a108
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0255
"stackalloc" darf nicht in einem catch\- oder finally\-Block verwendet werden.  
  
 Das [stackalloc](../Topic/stackalloc%20\(C%23%20Reference\).md)\-Schlüsselwort darf nicht in einem [catch](../Topic/try-catch%20\(C%23%20Reference\).md)\- oder [finally](../Topic/try-catch-finally%20\(C%23%20Reference\).md)\-Block verwendet werden. Weitere Informationen finden Sie unter [Ausnahmen und Ausnahmebehandlung](../Topic/Exceptions%20and%20Exception%20Handling%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0255 generiert:  
  
```  
// CS0255.cs // compile with: /unsafe using System; public class TestTryFinally { public static unsafe void Test() { int i = 123; string s = "Some string"; object o = s; try { // Conversion is not valid; o contains a string not an int i = (int) o; } finally { Console.Write("i = {0}", i); int* fib = stackalloc int[100];   // CS0255 } } public static void Main() { } }  
```