---
title: "Compilerfehler CS0525"
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
  - "CS0525"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0525"
ms.assetid: fcecfd4f-221f-41e6-a95c-1685be78926e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0525
Schnittstellen können keine Felder enthalten.  
  
 Eine [Schnittstelle](../Topic/interface%20\(C%23%20Reference\).md) kann Methoden und Eigenschaften, jedoch keine Felder enthalten.  
  
 Im folgenden Beispiel wird CS0525 generiert:  
  
```  
// CS0525.cs namespace x { public interface clx { public int i;   // CS0525 } }  
```