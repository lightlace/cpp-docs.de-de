---
title: "Compilerfehler CS1624"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS1624"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1624"
ms.assetid: af7d049d-27e2-4ce1-973c-5c2cb3e56a63
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1624
Der Text von 'accessor' kann kein Iteratorblock sein, da 'typ' kein Iteratorschnittstellentyp ist.  
  
 Dieser Fehler tritt auf, wenn eine Iteratorzugriffsmethode verwendet wird, der Rückgabetyp ist aber keiner der Iterator\-Schnittstellentypen: <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable`1>, <xref:System.Collections.IEnumerator>, <xref:System.Collections.Generic.IEnumerator`1>. Um diesen Fehler zu vermeiden, verwenden Sie einen der Iterator\-Schnittstellentypen als Rückgabetyp.  
  
## Beispiel  
 Im folgenden Beispiel wird CS1624 generiert:  
  
```  
// CS1624.cs using System; using System.Collections; class C { public int Iterator // Try this instead: // public IEnumerable Iterator { get  // CS1624 { yield return 1; } } }  
```