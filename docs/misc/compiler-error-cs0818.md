---
title: "Compilerfehler CS0818"
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
  - "CS0818"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0818"
ms.assetid: e4941018-a10a-4636-98ea-aade29e45728
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0818
Implizit typisierte lokale Variablen müssen initialisiert werden.  
  
 Eine implizit typisierte lokale Variable muss während der Deklaration gleichzeitig mit einem Wert initialisiert werden.  
  
### So beheben Sie diesen Fehler  
  
1.  Weisen Sie der Variablen einen Wert oder einen expliziten Typ zu.  
  
## Beispiel  
 Der folgende Code generiert CS0818:  
  
```  
// cs0818.cs class A { public static int Main() { var a; // CS0818 return -1; } }  
```  
  
## Siehe auch  
 [Implizit typisierte lokale Variablen](../Topic/Implicitly%20Typed%20Local%20Variables%20\(C%23%20Programming%20Guide\).md)