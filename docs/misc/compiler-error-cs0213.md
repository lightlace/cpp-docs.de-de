---
title: "Compilerfehler CS0213"
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
  - "CS0213"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0213"
ms.assetid: 3c1d55e3-2b84-4c28-8206-ef65869a898c
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0213
Sie können die fixed\-Anweisung nicht verwenden, um die Adresse eines bereits festen Ausdrucks abzurufen.  
  
 Eine lokale Variable in einer [unsafe](../Topic/unsafe%20\(C%23%20Reference\).md)\-Methode oder einem Parameter ist bereits "fixed" \(auf dem Stapel\), sodass Sie die Adresse keiner dieser beiden Variablen in einem [fixed](../Topic/fixed%20Statement%20\(C%23%20Reference\).md)\-Ausdruck verwenden können. Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../Topic/Unsafe%20Code%20and%20Pointers%20\(C%23%20Programming%20Guide\).md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS0213 generiert.  
  
```  
// CS0213.cs // compile with: /unsafe public class MyClass { unsafe public static void Main() { int i = 45; fixed (int *j = &i) { }  // CS0213 // try the following line instead // int* j = &i; int[] a = new int[] {1,2,3}; fixed (int *b = a) { fixed (int *c = b) { }  // CS0213 // try the following line instead // int *c = b; } } }  
```