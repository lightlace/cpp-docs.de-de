---
title: "Compilerwarnung (Stufe 2) CS1587"
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
  - "CS1587"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1587"
ms.assetid: b27c2009-d485-43fd-a649-fbc15570d256
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerwarnung (Stufe 2) CS1587
Der XML\-Kommentar ist auf keinem gültigen Sprachelement abgelegt.  
  
 Empfohlene Tags für Dokumentationskommentare sind nicht für alle Sprachelemente zulässig. Tags sind z. B. für Namespaces nicht zulässig. Weitere Informationen zu XML\-Kommentaren finden Sie unter [Empfohlene Tags für Dokumentationskommentare](../Topic/Recommended%20Tags%20for%20Documentation%20Comments%20\(C%23%20Programming%20Guide\).md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS1587 generiert:  
  
```  
// CS1587.cs // compile with: /W:2 /doc:x.xml /// <summary>test</summary>   // CS1587, tag not allowed on namespace namespace MySpace { class MyClass { public static void Main() { } } }  
```