---
title: "Compilerfehler CS0132"
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
  - "CS0132"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0132"
ms.assetid: e8ad1281-2912-4b6a-b2af-a319a23ddd16
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0132
'Konstruktor': Ein statischer Konstruktor muss parameterlos sein.  
  
 Ein [statischer](../Topic/static%20\(C%23%20Reference\).md) Konstruktor kann nicht mit einem oder mehreren Parametern deklariert werden. Weitere Informationen finden Sie unter [Konstruktoren](../Topic/Constructors%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0132 generiert:  
  
```  
// CS0132.cs namespace MyNamespace { public class MyClass { public MyClass(int i) { } } public class MyClass2 : MyClass { static MyClass2(int i)   // CS0132 { } } }  
```