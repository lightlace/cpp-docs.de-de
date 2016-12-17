---
title: "Compilerwarnung (Stufe 1) CS1634"
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
  - "CS1634"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1634"
ms.assetid: 4fd00eeb-89e3-4c18-827d-9b00a4bd8c9a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerwarnung (Stufe 1) CS1634
"disable" oder "restore" erwartet.  
  
 Dieser Fehler tritt auf, wenn eine „\#pragma warning“\-Klausel falsch formatiert wurde, wenn also beispielsweise „disable“ oder „restore“ weggelassen wurde. Weitere Informationen finden Sie unter der [\#pragma warning](../Topic/%23pragma%20warning%20\(C%23%20Reference\).md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS1634 generiert:  
  
```  
// CS1634.cs // compile with: /W:1 #pragma warning   // CS1634 // Try this instead: // #pragma warning disable 0219 class MyClass { public static void Main() { } }  
```