---
title: "Compilerfehler CS0527"
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
  - "CS0527"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0527"
ms.assetid: 1acd244b-c55b-424f-b038-a130d65b8685
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0527
Der Typ "Typ" in der Schnittstellenliste ist keine Schnittstelle.  
  
 Eine [Struktur](../Topic/struct%20\(C%23%20Reference\).md) oder [Schnittstelle](../Topic/interface%20\(C%23%20Reference\).md) kann von einer anderen Schnittstelle, aber nicht von irgendeinem anderen Typ erben.  
  
 Im folgenden Beispiel wird CS0527 generiert:  
  
```  
// CS0527.cs // compile with: /target:library public struct clx : int {}   // CS0527 int not an interface  
```