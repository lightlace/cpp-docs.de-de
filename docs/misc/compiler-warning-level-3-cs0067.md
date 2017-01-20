---
title: "Compilerwarnung (Stufe 3) CS0067"
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
  - "CS0067"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0067"
ms.assetid: df75220b-0b93-45ec-8655-98d9333b0bb7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerwarnung (Stufe 3) CS0067
Das Ereignis 'ereignis' wird niemals verwendet  
  
 Ein [Ereignis](../Topic/event%20\(C%23%20Reference\).md) wurde deklariert, aber zu keiner Zeit in der Klasse, in der es deklariert wurde, verwendet.  
  
 Im folgenden Beispiel wird CS0067 generiert:  
  
```  
// CS0067.cs // compile with: /W:3 using System; delegate void MyDelegate(); class MyClass { public event MyDelegate evt;   // CS0067 // uncomment TestMethod to resolve this CS0067 /* private void TestMethod() { if (evt != null) evt(); } */ public static void Main() { } }  
```