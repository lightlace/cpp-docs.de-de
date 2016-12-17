---
title: "Compilerfehler CS0155"
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
  - "CS0155"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0155"
ms.assetid: 6c92984a-2b10-453e-9cb7-e6a1d1b98aa6
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0155
Der aufgefangene oder ausgelöste Typ muss von System.Exception abgeleitet werden.  
  
 Es wurde versucht, einen Datentyp, der nicht von **System.Exception** abgeleitet wurde, an einen [catch](../Topic/try-catch%20\(C%23%20Reference\).md)\-Block zu übergeben. An einen **catch**\-Block können nur Datentypen übergeben werden, die von **System.Exception** abgeleitet wurden. Weitere Informationen finden Sie unter [Ausnahmebehandlungsanweisungen](../Topic/Exception%20Handling%20Statements%20\(C%23%20Reference\).md) und [Ausnahmen und Ausnahmebehandlung](../Topic/Exceptions%20and%20Exception%20Handling%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0155 generiert:  
  
```  
// CS0155.cs using System; namespace MyNamespace { public class MyClass2 // try the following line instead // public class MyClass2 : Exception { } public class MyClass { public static void Main() { try { } catch (MyClass2)   // CS0155, resolves if you derive MyClass2 from Exception { } } } }  
```