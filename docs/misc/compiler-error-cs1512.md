---
title: "Compilerfehler CS1512"
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
  - "CS1512"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1512"
ms.assetid: 50740d85-598d-478f-bfe3-e8c2e1a02ab8
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1512
Das base\-Schlüsselwort ist im aktuellen Kontext nicht verfügbar.  
  
 Das [base](../Topic/base%20\(C%23%20Reference\).md)\-Schlüsselwort wurde außerhalb einer Methode, Eigenschaft oder eines Konstruktors verwendet.  
  
 Im folgenden Beispiel wird der Fehler CS1512 generiert:  
  
```  
// CS1512.cs using System; class Base {} class CMyClass : Base { private String xx = base.ToString();   // CS1512 // Try putting this initialization in the constructor instead: // public CMyClass() // { //    xx = base.ToString(); // } public static void Main() { CMyClass z = new CMyClass(); } }  
```