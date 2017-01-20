---
title: "Compilerfehler CS1055"
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
  - "CS1055"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1055"
ms.assetid: a93cb577-95fc-490a-97c4-2f366409f2c3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1055
add\- oder remove\-Accessor erwartet.  
  
 Wenn Ihr [event](../Topic/event%20\(C%23%20Reference\).md)\-Element nicht als Feld deklariert ist, muss sowohl die **add**\- als auch die **remove**\-Accessorfunktion definiert werden.  
  
 Im folgenden Beispiel wird CS1055 generiert:  
  
```  
// CS1055.cs delegate void del(); class Test { public event del MyEvent { int i;   // CS1055 // uncomment accessors and delete previous line to resolve // add // { //    MyEvent += value; // } // remove // { //    MyEvent -= value; // } } public static void Main() { } }  
```