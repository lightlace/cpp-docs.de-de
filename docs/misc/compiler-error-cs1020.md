---
title: "Compilerfehler CS1020"
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
  - "CS1020"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1020"
ms.assetid: e8860769-a847-4248-a37b-77a59863467c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1020
Überladbarer binärer Operator erwartet.  
  
 Es wurde versucht, eine [Operatorüberladung](../Topic/Overloadable%20Operators%20\(C%23%20Programming%20Guide\).md) zu definieren, aber der Operator war kein binärer Operator, der zwei Parameter übernimmt.  
  
 Im folgenden Beispiel wird CS1020 generiert:  
  
```  
// CS1020.cs public class iii { public static int operator ++(iii aa, int bb)   // CS1020, change ++ to + { return 0; } public static void Main() { } }  
```