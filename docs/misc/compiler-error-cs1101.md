---
title: "Compilerfehler CS1101"
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
  - "CS1101"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1101"
ms.assetid: d6fc8834-eadf-4497-b442-0751895e6764
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1101
Der Parametermodifizierer „ref“ kann nicht mit „this“ verwendet werden.  
  
 Wird der erste Parameter einer statischen Methode durch das Schlüsselwort `this` geändert, wird dem Compiler signalisiert, dass die Methode eine Erweiterungsmethode ist. Für den ersten Parameter einer Erweiterungsmethode sind keine weiteren Modifizierer erforderlich oder zulässig.  
  
## Beispiel  
 Im folgenden Beispiel wird der Fehler CS1101 generiert:  
  
```  
// cs1101.cs // Compile with: /target:library public static class Extensions { // No type parameters. public static void Test(ref this int i) {} // CS1101 // Single type parameter. public static void Test<T>(ref this T t) {}// CS1101 // Multiple type parameters. public static void Test<T,U,V>(ref this U u) {}// CS1101 }  
```  
  
## Siehe auch  
 [Erweiterungsmethoden](../Topic/Extension%20Methods%20\(C%23%20Programming%20Guide\).md)   
 [this](../Topic/this%20\(C%23%20Reference\).md)   
 [ref](../Topic/ref%20\(C%23%20Reference\).md)