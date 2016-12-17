---
title: "Compilerfehler CS0145"
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
  - "CS0145"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0145"
ms.assetid: e5f9a90f-1700-4e6a-8f82-23d0c0287b85
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0145
Für ein Konstantenfeld muss ein Wert bereitgestellt werden.  
  
 Sie müssen eine [const](../Topic/const%20\(C%23%20Reference\).md)\-Variable initialisieren. Weitere Informationen finden Sie unter [Konstanten](../Topic/Constants%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0145 generiert:  
  
```  
// CS0145.cs class MyClass { const int i;   // CS0145 // try the following line instead // const int i = 0; public static void Main() { } }  
```