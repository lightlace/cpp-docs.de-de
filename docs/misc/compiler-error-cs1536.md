---
title: "Compilerfehler CS1536"
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
  - "CS1536"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1536"
ms.assetid: 65f14fbb-df79-4759-8911-93f8f90f5a60
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1536
Ungültiger Parametertyp "void".  
  
 Es ist nicht erforderlich oder zulässig, einen anderen [void](../Topic/void%20\(C%23%20Reference\).md)\-Parameter als einen void\-Zeiger anzugeben.  
  
 Im folgenden Beispiel wird CS1536 generiert:  
  
```  
// CS1536.cs class a { public static int x( void )   // CS1536 // try the following line instead // public static int x() { return 0; } public static void Main() { } }  
```