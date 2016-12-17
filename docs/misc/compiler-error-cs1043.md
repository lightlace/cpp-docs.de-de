---
title: "Compilerfehler CS1043"
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
  - "CS1043"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1043"
ms.assetid: 749703a1-d8ac-4be6-9c48-753f64ae92a1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1043
{ oder ; erwartet.  
  
 Ein Eigenschaftenaccessor wurde falsch deklariert. Weitere Informationen finden Sie unter [Verwenden von Eigenschaften](../Topic/Using%20Properties%20\(C%23%20Programming%20Guide\).md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS1043 generiert:  
  
```  
// CS1043.cs // compile with: /target:library public class MyClass { public int DoSomething { get return 1;   // CS1043 set {} } // OK public int DoSomething2 { get { return 1;} } }  
```