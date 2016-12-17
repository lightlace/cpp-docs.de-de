---
title: "Compilerfehler CS0544"
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
  - "CS0544"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0544"
ms.assetid: f8230a02-a666-4a1a-94cb-46f87463206a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0544
'Eigenschaftenüberschreibung': Überschreibung nicht möglich, da 'Nicht\-Eigenschaft' keine Eigenschaft ist.  
  
 Es wurde versucht, den Datentyp einer Nichteigenschaft als [Eigenschaft](../Topic/Properties%20\(C%23%20Programming%20Guide\).md) zu überschreiben. Das ist nicht zulässig.  
  
 Im folgenden Beispiel wird CS0544 generiert:  
  
```  
// CS0544.cs // compile with: /target:library public class a { public int i; } public class b : a { public override int i {   // CS0544 // try the following line instead // public new int i { get { return 0; } } }  
```