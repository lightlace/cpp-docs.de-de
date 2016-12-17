---
title: "Compilerfehler CS1524"
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
  - "CS1524"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1524"
ms.assetid: a7b80bbc-a2de-4718-b0f0-4c9526726525
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1524
"catch" oder "finally" erwartet.  
  
 Ein `try`\-Block muss von einem `catch`\- oder `finally`\-Block gefolgt werden.  
  
 Weitere Informationen zu Ausnahmen finden Sie unter [Ausnahmebehandlungsanweisungen](../Topic/Exception%20Handling%20Statements%20\(C%23%20Reference\).md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS1524 generiert:  
  
```  
// CS1524.cs class x { public static void Main() { try { // Code here } catch { } try { // Code here } finally { } try { // Code here } }     // CS1524, missing catch or finally }  
```