---
title: "Compilerfehler CS1620"
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
  - "CS1620"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1620"
ms.assetid: 13933976-218a-4fe2-8fde-5b9af522e2e5
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1620
Das Argument "Zahl" muss mit dem "Schlüsselwort"\-Schlüsselwort übergeben werden.  
  
 Dieser Fehler tritt auf, wenn Sie ein Argument an eine Funktion übergeben, die einen [ref](../Topic/ref%20\(C%23%20Reference\).md)\- oder [out](../Topic/out%20\(C%23%20Reference\).md)\-Parameter verwendet und Sie das `ref`\- oder `out`\-Schlüsselwort zum Zeitpunkt des Aufrufs nicht angegeben oder das falsche Schlüsselwort verwendet haben. Aus dem Fehlertext geht hervor, welches Schlüsselwort zu verwenden ist und welches Argument den Fehler verursacht hat.  
  
 Im folgenden Beispiel wird CS1620 generiert:  
  
```  
// CS1620.cs class C { void f(ref int i) {} public static void Main() { int x = 1; f(out x);  // CS1620 – f takes a ref parameter, not an out parameter // Try this line instead: // f(ref x); } }  
```