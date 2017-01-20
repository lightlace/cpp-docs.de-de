---
title: "Compilerfehler CS0547"
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
  - "CS0547"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0547"
ms.assetid: aa80873f-deb0-4ff2-8435-92a626bb5b80
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0547
'property': Die Eigenschaft oder der Indexer dürfen nicht den void\-Typ aufweisen.  
  
 [void](../Topic/void%20\(C%23%20Reference\).md) als Rückgabewert für eine Eigenschaft ist ungültig.  
  
 Weitere Informationen finden Sie unter [Eigenschaften](../Topic/Properties%20\(C%23%20Programming%20Guide\).md).  
  
 Das folgende Beispiel generiert CS0547:  
  
```  
// CS0547.cs public class a { public void i   // CS0547 // Try the following declaration instead: // public int i { get { return 0; } } } public class b : a { public static void Main() { } }  
```