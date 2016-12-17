---
title: "Compilerfehler CS1040"
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
  - "CS1040"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1040"
ms.assetid: a988d665-ead5-489f-922d-ff2c4dd8a922
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1040
Präprozessordirektiven müssen das erste Zeichen in einer Zeile sein, das keine Leerstelle ist.  
  
 In einer Zeile wurde eine [Präprozessordirektive](../Topic/C%23%20Preprocessor%20Directives.md) gefunden, war aber nicht das erste Token in der Zeile. Eine Direktive muss das erste Token in der Zeile sein.  
  
 Im folgenden Beispiel wird CS1040 generiert:  
  
```  
// CS1040.cs /* Define a symbol, X */ #define X   // CS1040 // try the following two lines instead // /* Define a symbol, X */ // #define X public class MyClass { public static void Main() { } }  
```