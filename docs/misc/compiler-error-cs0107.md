---
title: "Compilerfehler CS0107"
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
  - "CS0107"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0107"
ms.assetid: 505763c5-6d68-4c57-a8bd-7b03682da4c5
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0107
Mehr als ein Schutzmodifizierer.  
  
 Für einen Klassenmember ist nur ein Zugriffsmodifizierer \([public](../Topic/public%20\(C%23%20Reference\).md), [private](../Topic/private%20\(C%23%20Reference\).md), [protected](../Topic/protected%20\(C%23%20Reference\).md) oder [internal](../Topic/internal%20\(C%23%20Reference\).md)\) zulässig, mit Ausnahme von **internal protected**.  
  
 Im folgenden Beispiel wird CS0107 generiert:  
  
```  
// CS0107.cs public class C { private internal void f()   // CS0107, delete private or internal { } public static int Main() { return 1; } }  
```