---
title: "Compilerfehler CS1105"
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
  - "CS1105"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1105"
ms.assetid: fcbd91ad-a76a-4b22-868d-16824fa96f85
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1105
Erweiterungsmethoden müssen statisch sein.  
  
 Erweiterungsmethoden müssen als statische Methoden in einer nicht generischen statischen Klasse deklariert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird der Fehler CS1105 generiert, da `Test` nicht statisch ist:  
  
```  
// cs1105.cs // Compile with: /target:library public class Extensions { // Single type parameter. public void Test<T>(this System.String s) {} //CS1105 }  
```  
  
## Siehe auch  
 [Erweiterungsmethoden](../Topic/Extension%20Methods%20\(C%23%20Programming%20Guide\).md)   
 [Statische](../Topic/static%20\(C%23%20Reference\).md)