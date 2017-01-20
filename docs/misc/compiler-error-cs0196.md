---
title: "Compilerfehler CS0196"
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
  - "CS0196"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0196"
ms.assetid: d361484e-73b8-439a-99c7-714e61d73755
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0196
Ein Zeiger darf nur von einem Wert indiziert werden.  
  
 Ein Zeiger kann nicht über mehrere Indizes verfügen. Weitere Informationen finden Sie unter [Zeigertypen](../Topic/Pointer%20types%20\(C%23%20Programming%20Guide\).md)  
  
 Im folgenden Beispiel wird CS0196 generiert:  
  
```  
// CS0196.cs public class MyClass { public static void Main () { int *i = null; int j = 0; j = i[1,2];   // CS0196 // try the following line instead // j = i[1]; } }  
```