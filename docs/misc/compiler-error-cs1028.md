---
title: "Compilerfehler CS1028"
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
  - "CS1028"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1028"
ms.assetid: 9df07db3-256f-45e9-8323-26539c55a1d8
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1028
Unerwartete Präprozessordirektive.  
  
 Eine [Präprozessordirektive](../Topic/C%23%20Preprocessor%20Directives.md) wurde gefunden, aber nicht erwartet.  
  
 Beispielsweise wurde `#endif` ohne vorangestellte `#if` gefunden.  
  
 Im folgenden Beispiel wird CS1028 generiert:  
  
```  
// CS1028.cs #endif   // CS1028, no matching #if namespace x { public class clx { public static void Main() { } } }  
```