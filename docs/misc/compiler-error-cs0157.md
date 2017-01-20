---
title: "Compilerfehler CS0157"
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
  - "CS0157"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0157"
ms.assetid: a5d9d506-81f8-47dd-85b6-85f8170bcbef
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0157
Das Steuerelement kann den Text einer finally\-Klausel nicht verlassen.  
  
 Alle Anweisungen in einer [finally](../Topic/try-catch-finally%20\(C%23%20Reference\).md)\-Klausel müssen ausgeführt werden. Weitere Informationen finden Sie unter [Ausnahmebehandlungsanweisungen](../Topic/Exception%20Handling%20Statements%20\(C%23%20Reference\).md) und [Ausnahmen und Ausnahmebehandlung](../Topic/Exceptions%20and%20Exception%20Handling%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0157 generiert:  
  
```  
// CS0157.cs using System; namespace MyNamespace { public class MyClass2 : Exception { } public class MyClass { public static void Main() { try { } finally { return;   // CS0157, cannot leave finally clause } } } }  
```