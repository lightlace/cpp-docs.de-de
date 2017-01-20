---
title: "Compilerfehler CS0543"
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
  - "CS0543"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0543"
ms.assetid: f85e09a7-0e08-4dea-8f64-218c0876e4f6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0543
'Enumeration': Der Enumeratorwert ist zu groß für seinen Typ.  
  
 Ein Wert, der einem Element in einer [Enumeration](../Topic/enum%20\(C%23%20Reference\).md) zugewiesen wurde, liegt außerhalb des Bereichs des Datentyps.  
  
 Im folgenden Beispiel wird CS0543 generiert:  
  
```  
// CS0543.cs namespace x { enum I : byte {a = 255, b, c}   // CS0543 public class clx { public static int Main() { return 0; } } }  
```