---
title: "Compilerfehler CS1017"
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
  - "CS1017"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1017"
ms.assetid: e0902e8a-b042-4711-a8a6-83456a3f88cb
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1017
Catch\-Klauseln können nicht auf die allgemeine catch\-Klausel einer try\-Anweisung folgen.  
  
 Ein `catch`\-Block, der keine Parameter annimmt, muss der letzte in einer Reihe von `catch`\-Blöcken sein. Weitere Informationen zu Ausnahmen finden Sie unter [Ausnahmebehandlungsanweisungen](../Topic/Exception%20Handling%20Statements%20\(C%23%20Reference\).md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS1017 generiert:  
  
```  
// CS1017.cs using System; namespace x { public class b : Exception { } public class a { public static void Main() { try { } catch   // CS1017, must be last catch { } catch(b) { throw; } } } }  
```