---
title: "Compilerfehler CS0156"
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
  - "CS0156"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0156"
ms.assetid: 32026b1b-bcd7-4464-b63f-3b38c00452a6
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0156
In einer finally\-Klausel, die in der nächsten einschließenden catch\-Klausel geschachtelt ist, ist keine throw\-Anweisung ohne Argumente zulässig.  
  
 Eine [throw](../Topic/throw%20\(C%23%20Reference\).md)\-Anweisung ohne Parameter kann nur in einer **catch**\-Klausel vorkommen, die keine Parameter annimmt.  
  
 Weitere Informationen finden Sie unter [Ausnahmebehandlungsanweisungen](../Topic/Exception%20Handling%20Statements%20\(C%23%20Reference\).md) und [Ausnahmen und Ausnahmebehandlung](../Topic/Exceptions%20and%20Exception%20Handling%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0156 generiert:  
  
```  
// CS0156.cs using System; namespace MyNamespace { public class MyClass2 : Exception { } public class MyClass { public static void Main() { try { throw;   // CS0156 } catch(MyClass2) { throw;   // this throw is valid } } } }  
```