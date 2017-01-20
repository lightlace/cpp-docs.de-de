---
title: "Compilerfehler CS0653"
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
  - "CS0653"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0653"
ms.assetid: c94043b9-b5d9-4294-921d-a4aead124d44
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0653
Die Attributklasse "Klasse" kann nicht angewendet werden, weil sie abstrakt ist  
  
 Eine [abstrakte](../Topic/abstract%20\(C%23%20Reference\).md) benutzerdefinierte Attributklasse kann nicht als Attribut verwendet werden.  
  
 Im folgenden Beispiel wird CS0653 generiert:  
  
```  
// CS0653.cs using System; public abstract class MyAttribute : Attribute { } public class My2Attribute : MyAttribute { } [My]   // CS0653 // try the following line instead // [My2] class MyClass { public static void Main() { } }  
```