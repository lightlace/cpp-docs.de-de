---
title: "Compilerfehler CS0144"
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
  - "CS0144"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0144"
ms.assetid: 3904cab1-05bd-44ec-81d0-e36c5656f742
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0144
Es konnte keine Instanz der abstrakten Klasse oder Schnittstelle "Schnittstelle" erstellt werden  
  
 Sie können keine Instanz einer [abstrakten](../Topic/abstract%20\(C%23%20Reference\).md) Klasse oder einer [Schnittstelle](../Topic/interface%20\(C%23%20Reference\).md) erstellen. Weitere Informationen finden Sie unter [Schnittstellen](../Topic/Interfaces%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0144 generiert:  
  
```  
// CS0144.cs interface MyInterface { } public class MyClass { public static void Main() { MyInterface myInterface = new MyInterface ();   // CS0144 } }  
```