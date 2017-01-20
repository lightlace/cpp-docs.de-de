---
title: "Compilerfehler CS0666"
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
  - "CS0666"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0666"
ms.assetid: 44ad4574-b4a2-487b-8d05-0116762231ab
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0666
'Member': In der Struktur wurde ein neuer geschützter Member deklariert.  
  
 Eine [Struktur](../Topic/struct%20\(C%23%20Reference\).md) kann nicht [abstrakt](../Topic/abstract%20\(C%23%20Reference\).md) sein und ist immer implizit [versiegelt](../Topic/sealed%20\(C%23%20Reference\).md). Da Strukturen keine Vererbung unterstützen, ist das Konzept eines [geschützten](../Topic/protected%20\(C%23%20Reference\).md) Member in einer Struktur nicht sinnvoll. Weitere Informationen finden Sie unter [Vererbung](../Topic/Inheritance%20\(C%23%20Programming%20Guide\).md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS0666 generiert:  
  
```  
// CS0666.cs class M { static void Main() { } } struct S { protected int x;   // CS0666 }  
```