---
title: "Compilerfehler CS0502"
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
  - "CS0502"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0502"
ms.assetid: 6cd6deda-73a1-42d8-893b-45a685e63380
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0502
"Member" kann nicht gleichzeitig abstrakt und versiegelt sein  
  
 Ein Klassenmember kann nicht gleichzeitig [abstrakt](../Topic/abstract%20\(C%23%20Reference\).md) und [versiegelt](../Topic/sealed%20\(C%23%20Reference\).md) sein.  
  
 Im folgenden Beispiel wird CS0502 generiert:  
  
```  
// CS0502.cs public class B { abstract public void F(); } public class C : B { abstract sealed override public void F()   // CS0502 { } } public class CMain { public static void Main() { } }  
```