---
title: "Compilerfehler CS0541"
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
  - "CS0541"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0541"
ms.assetid: ed812c07-24f7-43c6-9a44-553f27f6249d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0541
'Deklaration': Eine explizite Schnittstellendeklaration kann nur in einer Klasse oder einer Struktur deklariert werden.  
  
 Eine explizite [Schnittstellendeklaration](../Topic/interface%20\(C%23%20Reference\).md) wurde außerhalb einer [Klasse](../Topic/class%20\(C%23%20Reference\).md) oder [Struktur](../Topic/struct%20\(C%23%20Reference\).md) gefunden.  
  
 Im folgenden Beispiel wird CS0541 generiert:  
  
```  
// CS0541.cs namespace x { interface IFace { void F(); } interface IFace2 : IFace { void IFace.F();   // CS0541 } }  
```