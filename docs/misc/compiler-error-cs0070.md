---
title: "Compilerfehler CS0070"
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
  - "CS0070"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0070"
ms.assetid: bb0de7c6-c734-4a8f-ab62-0a50eac2a91f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0070
Das Ereignis 'Ereignis' kann nur links von '\+\=' oder '\-\=' stehen \(es sei denn, es wird innerhalb des Typs 'Typ' verwendet\).  
  
 Außerhalb der Klasse, in der es definiert ist, kann ein [Ereignis](../Topic/event%20\(C%23%20Reference\).md) Verweise nur addieren oder subtrahieren. Weitere Informationen finden Sie unter [Ereignisse](../Topic/Events%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0070 generiert:  
  
```  
// CS0070.cs using System; public delegate void EventHandler(); public class A { public event EventHandler Click; public static void OnClick() { EventHandler eh; A a = new A(); eh = a.Click; } public static void Main() { } } public class B { public int Foo () { EventHandler eh = new EventHandler(A.OnClick); A a = new A(); eh = a.Click;   // CS0070 // try the following line instead // a.Click += eh; return 1; } }  
```