---
title: "Compilerfehler CS0133"
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
  - "CS0133"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0133"
ms.assetid: b5be456f-824d-4e6d-802b-0b1b5889efbd
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0133
Der Ausdruck, der 'Variable' zugewiesen wird, muss konstant sein.  
  
 Eine [const](../Topic/const%20\(C%23%20Reference\).md)\-Variable kann keinen Ausdruck als ihren Wert übernehmen, der nicht konstant ist. Weitere Informationen finden Sie unter [Konstanten](../Topic/Constants%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0133 generiert:  
  
```  
// CS0133.cs public class MyClass { public const int i = c;   // CS0133, c is not constant public static int c = i; // try the following line instead // public const int i = 6; public static void Main() { } }  
```