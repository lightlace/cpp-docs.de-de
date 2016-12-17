---
title: "Compilerfehler CS0069"
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
  - "CS0069"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0069"
ms.assetid: a1b32906-7773-47c6-8515-162a201a9be5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0069
Ein Ereignis in einer Schnittstelle kann keine add\- oder remove\-Accessoren haben.  
  
 Sie können die Accessorfunktionen eines Ereignisses nicht in einer [Schnittstelle](../Topic/interface%20\(C%23%20Reference\).md) definieren. Weitere Informationen finden Sie unter [Ereignisse](../Topic/Events%20\(C%23%20Programming%20Guide\).md) und [Schnittstellen](../Topic/Interfaces%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0069 generiert:  
  
```  
// CS0069.cs // compile with: /target:library public delegate void EventHandler(); public interface a { event EventHandler Click { remove {} }   // CS0069 event EventHandler Click2;   // OK }  
```