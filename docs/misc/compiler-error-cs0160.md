---
title: "Compilerfehler CS0160"
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
  - "CS0160"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0160"
ms.assetid: 4ef07061-8ef5-42d9-b043-3f81307d569f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0160
Eine vorherige Catch\-Klausel hat bereits alle Ausnahmen dieses oder eines übergeordneten Typs abgefangen \(„type“\).  
  
 Eine Reihe von **catch**\-Anweisungen muss in absteigender Reihenfolge der Ableitung angegeben sein. Die meisten abgeleiteten Objekte müssen beispielsweise zuerst angezeigt werden.  
  
 Weitere Informationen finden Sie unter [Ausnahmebehandlungsanweisungen](../Topic/Exception%20Handling%20Statements%20\(C%23%20Reference\).md) und [Ausnahmen und Ausnahmebehandlung](../Topic/Exceptions%20and%20Exception%20Handling%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0160 generiert:  
  
```  
// CS0160.cs public class MyClass2 : System.Exception {} public class MyClass { public static void Main() { try {} catch(System.Exception) {}   // Second-most derived; should be second catch catch(MyClass2) {}   // CS0160  Most derived; should be first catch } }  
```