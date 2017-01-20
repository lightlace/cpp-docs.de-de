---
title: "Compilerfehler CS0678"
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
  - "CS0678"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0678"
ms.assetid: ca389fc9-da78-4e16-b68c-782f90b17c83
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0678
"Variable": Ein Feld kann nicht gleichzeitig flüchtig und schreibgeschützt sein  
  
 Die Schlüsselwörter [volatile](../Topic/volatile%20\(C%23%20Reference\).md) und [readonly](../Topic/readonly%20\(C%23%20Reference\).md) schließen sich gegenseitig aus.  
  
 Im folgenden Beispiel wird CS0678 generiert:  
  
```  
// CS0678.cs using System; class TestClass { private readonly volatile int i;   // CS0678 // try the following line instead // private volatile int i; public static void Main() { } }  
```