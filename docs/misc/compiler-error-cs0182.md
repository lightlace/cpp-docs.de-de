---
title: "Compilerfehler CS0182"
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
  - "CS0182"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0182"
ms.assetid: a9e97bb8-f06e-499f-aadf-26abc2082f98
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0182
Ein Attributargument muss ein constant\-, typeof\- oder Arrayerstellungsausdruck eines Attributparametertyps sein.  
  
 Bestimmte Einschränkungen legen fest, welche Arten von Argumenten mit Attributen verwendet werden können. Beachten Sie, dass zusätzlich zu den in der Fehlermeldung angegebenen Einschränkungen die folgenden Typen NICHT als Attributargumente zulässig sind:  
  
-   [sbyte](../Topic/sbyte%20\(C%23%20Reference\).md)  
  
-   [ushort](../Topic/ushort%20\(C%23%20Reference\).md)  
  
-   [uint](../Topic/uint%20\(C%23%20Reference\).md)  
  
-   [ulong](../Topic/ulong%20\(C%23%20Reference\).md)  
  
-   [decimal](../Topic/decimal%20\(C%23%20Reference\).md)  
  
 Weitere Informationen finden Sie unter [NICHT IM BUILD: Globale Attribute \(C\#\-Programmierhandbuch\)](assetId:///7c6c41f8-f0d5-4345-8987-3d91f9bae136).  
  
## Beispiel  
 Im folgenden Beispiel wird CS0182 generiert:  
  
```  
// CS0182.cs public class MyClass { static string s = "Test"; [System.Diagnostics.ConditionalAttribute(s)]   // CS0182 // try the following line instead // [System.Diagnostics.ConditionalAttribute("Test")] void NonConstantArgumentToConditional() { } public static void Main() { } }  
```