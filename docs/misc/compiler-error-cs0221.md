---
title: "Compilerfehler CS0221"
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
  - "CS0221"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0221"
ms.assetid: 97170b49-54f1-4dac-a865-2f9cc6bf55b1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0221
Der Konstantenwert "Wert" kann nicht in "Typ" konvertiert werden. \(Verwenden Sie zum Überschreiben die unchecked\-Syntax.\)  
  
 [checked](../Topic/checked%20\(C%23%20Reference\).md) \(standardmäßig aktiviert\) hat eine Zuweisungsoperation erkannt, die zu Datenverlust führen würde. Korrigieren Sie die Zuweisung, oder verwenden Sie [unchecked](../Topic/unchecked%20\(C%23%20Reference\).md), um diesen Fehler zu beheben. Weitere Informationen finden Sie unter [Checked und Unchecked](../Topic/Checked%20and%20Unchecked%20\(C%23%20Reference\).md).  
  
 Im folgenden Beispiel wird CS0221 generiert:  
  
```  
// CS0221.cs public class MyClass { public static void Main() { // unchecked // { int a = (int)0xFFFFFFFF;   // CS0221 a++; // } } }  
```