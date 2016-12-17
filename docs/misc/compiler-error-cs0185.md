---
title: "Compilerfehler CS0185"
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
  - "CS0185"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0185"
ms.assetid: d6546e10-0af3-4860-8e6f-2da7dbeb3d28
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0185
„type“ ist kein Verweistyp, wie er für die lock\-Anweisung erforderlich ist.  
  
 Die [lock](../Topic/lock%20Statement%20\(C%23%20Reference\).md)\-Anweisung kann nur Verweistypen auswerten. Weitere Informationen finden Sie unter [Threadsynchronisierung](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md) und [Verweistypen](../Topic/Reference%20Types%20\(C%23%20Reference\).md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS0185 generiert:  
  
```  
// CS0185.cs public class MainClass { public static void Main () { lock (1)   // CS0185 // try the following lines instead // MainClass x = new MainClass(); // lock(x) { } } }  
```