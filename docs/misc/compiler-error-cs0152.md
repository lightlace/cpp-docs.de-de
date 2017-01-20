---
title: "Compilerfehler CS0152"
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
  - "CS0152"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0152"
ms.assetid: 4915ca16-6485-4e1f-ace0-c71a7b339ba4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0152
Die Bezeichnung „label“ kommt bereits in dieser switch\-Anweisung vor.  
  
 Eine Bezeichnung wurde in einer [switch](../Topic/switch%20\(C%23%20Reference\).md)\-Anweisung wiederholt. Weitere Informationen finden Sie unter [switch](../Topic/switch%20\(C%23%20Reference\).md).  
  
 Im folgenden Beispiel wird CS0152 generiert:  
  
```  
// CS0152.cs namespace MyNamespace { public class MyClass { public static void Main() { int i = 0; switch (i) { case 1: i++; return; case 1:   // CS0152, two case 1 statements i++; return; } } } }  
```