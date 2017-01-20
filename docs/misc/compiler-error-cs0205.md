---
title: "Compilerfehler CS0205"
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
  - "CS0205"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0205"
ms.assetid: 616d98cf-e7a5-4f8e-93da-fcd6e1e4de35
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0205
Ein abstrakter Basismember kann nicht aufgerufen werden: 'Methode'  
  
 Sie können eine [bstrakte](../Topic/abstract%20\(C%23%20Reference\).md) Methode nicht aufrufen, da sie keinen Methodentext besitzt. Weitere Informationen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../Topic/Abstract%20and%20Sealed%20Classes%20and%20Class%20Members%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0205 generiert:  
  
```  
// CS0205.cs abstract public class MyClass { abstract public void M(); } public class MyClass2 : MyClass { public override void M() { base.M();   // CS0205, delete this line } public static void Main() { } }  
```