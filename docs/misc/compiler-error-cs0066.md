---
title: "Compilerfehler CS0066"
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
  - "CS0066"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0066"
ms.assetid: 9b50b49b-78b8-4562-8839-d59e5edbec6b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0066
"Ereignis": Das Ereignis muss einen Delegattyp aufweisen.  
  
 Das Schlüsselwort "event" erfordert einen [Delegat](../Topic/delegate%20\(C%23%20Reference\).md)typ. Weitere Informationen finden Sie unter [Ereignisse](../Topic/Events%20\(C%23%20Programming%20Guide\).md) und [Delegaten](../Topic/Delegates%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0066 generiert:  
  
```  
// CS0066.cs using System; public class EventHandler { } // to fix the error, remove the event declaration and the // EventHandler class declaration, and uncomment the following line // public delegate void EventHandler(); public class a { public event EventHandler Click;   // CS0066 private void TestMethod() { if (Click != null) Click(); } public static void Main() { } }  
```