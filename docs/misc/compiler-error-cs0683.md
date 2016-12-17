---
title: "Compilerfehler CS0683"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0683"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0683"
ms.assetid: 04cca66d-8a0b-469a-b157-9c8ece368c48
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0683
Die explizite Methodenimplementierung "explizite\_Methode" ist ein Accessor und kann "Methode" daher nicht implementieren.  
  
 Im folgenden Beispiel wird CS0683 generiert:  
  
```  
// CS0683.cs interface IExample { int Test { get; } } class CExample : IExample { int IExample.get_Test() { return 0; } // CS0683 int IExample.Test { get{ return 0; } } // correct }  
```