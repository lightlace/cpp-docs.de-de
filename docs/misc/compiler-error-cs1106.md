---
title: "Compilerfehler CS1106"
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
  - "CS1106"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1106"
ms.assetid: 3585600a-6b2c-47aa-a418-ef049f07c107
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1106
Erweiterungsmethoden müssen in einer nicht generischen statischen Klasse definiert werden.  
  
 Erweiterungsmethoden müssen als statische Methoden in einer nicht generischen statischen Klasse definiert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird CS1106 generiert, weil die `Extensions`\-Klasse nicht als `static` definiert wurde:  
  
```  
// cs1106.cs public class Extensions // CS1106 { public  static void Test<T>(this System.String s) {} }  
```  
  
## Siehe auch  
 [Erweiterungsmethoden](../Topic/Extension%20Methods%20\(C%23%20Programming%20Guide\).md)   
 [Statische](../Topic/static%20\(C%23%20Reference\).md)