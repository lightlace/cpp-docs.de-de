---
title: "Compilerfehler CS1558"
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
  - "CS1558"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1558"
ms.assetid: ee603d66-007e-4782-9285-7ff031975f0f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1558
'Klasse' hat keine passende statische Main\-Methode.  
  
 Die [\/main](../Topic/-main%20\(C%23%20Compiler%20Options\).md)\-Compileroption hat eine Klasse angegeben, in der nach einer **Main**\-Methode gesucht werden soll. Die [Main](../Topic/Main\(\)%20and%20Command-Line%20Arguments%20\(C%23%20Programming%20Guide\).md)\-Methode wurde jedoch nicht ordnungsgemäß definiert.  
  
 Im folgende Beispiel wird CS1558 aufgrund eines ungültigen Rückgabetyps generiert.  
  
```  
// CS1558.cs // compile with: /main:MyNamespace.MyClass namespace MyNamespace { public class MyClass { public static float Main() { return 0.0; // CS1558 because the return type is a float. } } }  
```