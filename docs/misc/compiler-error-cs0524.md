---
title: "Compilerfehler CS0524"
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
  - "CS0524"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0524"
ms.assetid: a5cd8fb0-f5df-4580-9116-a6be4dffd1cb
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0524
„type“: Schnittstellen können keine Typen deklarieren.  
  
 Eine [Schnittstelle](../Topic/interface%20\(C%23%20Reference\).md) darf keinen benutzerdefinierten Typ, sondern nur Methoden und Eigenschaften enthalten.  
  
## Beispiel  
 Im folgenden Beispiel wird CS0524 generiert:  
  
```  
// CS0524.cs public interface Clx { public class Cly   // CS0524, delete user-defined type { } }  
  
```