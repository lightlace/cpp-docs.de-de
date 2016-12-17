---
title: "Compilerfehler CS0254"
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
  - "CS0254"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0254"
ms.assetid: 85b2ab1e-0011-4f1d-9181-76b9c9f3d914
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0254
Die rechte Seite einer fixed\-Anweisungszuweisung darf kein Umwandlungsausdruck sein.  
  
 Auf der rechten Seite eines [fixed](../Topic/fixed%20Statement%20\(C%23%20Reference\).md)\-Ausdrucks darf keine Umwandlung verwendet werden. Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../Topic/Unsafe%20Code%20and%20Pointers%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0254 generiert:  
  
```  
// CS0254.cs // compile with: /unsafe class Point { public uint x, y; } class FixedTest { unsafe static void SquarePtrParam (int* p) { *p *= *p; } unsafe public static void Main() { Point pt = new Point(); pt.x = 5; pt.y = 6; fixed (int* p = (int*)&pt.x)   // CS0254 // try the following line instead // fixed (uint* p = &pt.x) { SquarePtrParam ((int*)p); } } }  
```