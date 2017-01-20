---
title: "Compilerfehler CS0139"
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
  - "CS0139"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0139"
ms.assetid: 235ba3d4-566c-4ef6-801a-a338f4f2a12d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0139
Keine einschließende Schleife, aus der angehalten und fortgefahren werden kann.  
  
 Eine break\- oder continue\-Anweisung wurde außerhalb einer Schleife gefunden.  
  
 Weitere Informationen finden Sie unter [Sprunganweisungen](../Topic/Jump%20Statements%20\(C%23%20Reference\).md).  
  
 Im folgenden Beispiel wird CS0139 generiert:  
  
```  
// CS0139.cs namespace x { public class a { public static void Main() { continue;  // CS0139 break;     // CS0139 } } }  
```