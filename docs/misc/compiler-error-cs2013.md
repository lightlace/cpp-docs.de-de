---
title: "Compilerfehler CS2013"
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
  - "CS2013"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2013"
ms.assetid: 8a57b4c8-02fc-4f73-b489-121ff468c17d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS2013
Ungültige Bildbasisnummer "Wert"  
  
 An die Compileroption [\/baseaddress](../Topic/-baseaddress%20\(C%23%20Compiler%20Options\).md) wurde ein ungültiger Wert \(keine Zahl\) übergeben.  
  
 Im folgenden Beispiel wird CS2013 generiert:  
  
```  
// CS2013.cs // compile with: /target:library /baseaddress:x // CS2013 expected class MyClass { }  
```