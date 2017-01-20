---
title: "Compilerfehler CS0035"
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
  - "CS0035"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0035"
ms.assetid: a622113e-98a4-4583-992c-1fb55139320a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0035
Der Operator „operator“ ist bei einem Operanden vom Typ „type“ mehrdeutig.  
  
 Der Compiler unterstützt verschiedene Konvertierungen und kann nicht entscheiden, welche er vor dem Anwenden des Operators auswählen soll. Weitere Informationen finden Sie unter [Benutzerdefinierte Konvertierungen mit Vorlagen](../misc/templated-user-defined-conversions.md) und [Konvertierungsoperatoren](../Topic/Conversion%20Operators%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0035 generiert:  
  
```  
// CS0035.cs class MyClass { private int i; public MyClass(int i) { this.i = i; } public static implicit operator double(MyClass x) { return (double) x.i; } public static implicit operator decimal(MyClass x) { return (decimal) x.i; } } class MyClass2 { static void Main() { MyClass x = new MyClass(7); object o = - x;   // CS0035 // try a cast: // object o = - (double)x; } }  
  
```