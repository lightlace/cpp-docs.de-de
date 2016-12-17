---
title: "Compilerfehler CS1025"
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
  - "CS1025"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1025"
ms.assetid: 491c186f-cb40-47a9-9656-44fadfa18ae2
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1025
Einzeiliger Kommentar oder Zeilenende erwartet.  
  
 Eine Zeile mit einer [Präprozessordirektive](../Topic/C%23%20Preprocessor%20Directives.md) kann keinen mehrzeiligen Kommentar enthalten.  
  
 Im folgenden Beispiel wird CS1025 generiert:  
  
```  
#if true /* hello */   // CS1025 #endif   // this is a good comment  
```  
  
 CS1025 kann auch auftreten, wenn Sie wie folgt versuchen, eine ungültige Präprozessordirektive zu verwenden:  
  
```  
// CS1025.cs #define a class Sample { static void Main() { #if a 1   // CS1025, invalid syntax System.Console.WriteLine("Hello, World!"); #endif } }  
```