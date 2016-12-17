---
title: "Compilerfehler CS0176"
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
  - "CS0176"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0176"
ms.assetid: 783c13d8-5ac3-4aeb-bd63-0468cb05550d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0176
Auf den statischen Member "member" kann nicht mit einem Instanzenverweis zugegriffen werden. Qualifizieren Sie ihn stattdessen mit einem Typnamen  
  
 Nur ein Klassenname kann zum Qualifizieren einer [statischen](../Topic/static%20\(C%23%20Reference\).md) Variablen verwendet werden; ein Instanzenname kann kein Qualifizierer sein. Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../Topic/Static%20Classes%20and%20Static%20Class%20Members%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0176 generiert:  
  
```  
// CS0176.cs public class MyClass2 { public static int num; } public class Test { public static void Main() { MyClass2 mc2 = new MyClass2(); int i = mc2.num;   // CS0176 // try the following line instead // int i = MyClass2.num; } }  
  
```