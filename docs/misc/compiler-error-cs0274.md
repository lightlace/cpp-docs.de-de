---
title: "Compilerfehler CS0274"
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
  - "CS0274"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0274"
ms.assetid: bbd2d64e-a756-4713-b9ed-711d50b65e00
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0274
Es können keine Zugriffsmodifizierer für beide Accessoren der Eigenschaft oder des Indexers 'property\/indexer' angegeben werden.  
  
 Dieser Fehler tritt auf, wenn Sie eine Eigenschaft oder einen Indexer mit Zugriffsmodifizierern für beide Accessoren verwenden. Verwenden Sie einen Zugriffsmodifizierer nur für einen der beiden Accessoren, um diesen Fehler zu beheben. Weitere Informationen finden Sie unter [Accessorzugriff](../Topic/Restricting%20Accessor%20Accessibility%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird der Fehler CS0274 generiert:  
  
```  
// CS0274.cs public class MyClass { public int Property   // CS0274 { public get { return 0; } protected set { } } }  
```