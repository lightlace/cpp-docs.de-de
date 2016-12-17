---
title: "Compilerfehler CS0674"
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
  - "CS0674"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0674"
ms.assetid: 9ebfac30-6de8-4503-b4f0-d79f7398e3d5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0674
Verwenden Sie nicht "System.ParamArrayAttribute". Verwenden Sie stattdessen das Schlüsselwort "params".  
  
 Der C\#\-Compiler lässt die Verwendung von <xref:System.ParamArrayAttribute?displayProperty=fullName> nicht zu; verwenden Sie stattdessen [params](../Topic/params%20\(C%23%20Reference\).md).  
  
 Im folgenden Beispiel wird CS0674 generiert:  
  
```  
// CS0674.cs using System; public class MyClass { public static void UseParams([ParamArray] int[] list)   // CS0674 // try the following line instead // public static void UseParams(params int[] list) { for ( int i = 0 ; i < list.Length ; i++ ) Console.WriteLine(list[i]); Console.WriteLine(); } public static void Main() { UseParams(1, 2, 3); } }  
```