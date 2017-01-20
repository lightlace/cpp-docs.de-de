---
title: "Compilerfehler CS0241"
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
  - "CS0241"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Standardwerte für Methodenparameter"
  - "Standardwerte, Parameterwerte"
  - "Standardwerte, Methodenparameterwerte"
  - "Standardparameterwerte"
  - "CS0241"
ms.assetid: be31b194-3de5-4aab-b23a-6cf790f940ab
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0241
Spezifizierer für Standardparameter sind nicht zulässig.  
  
 [Methodenparameters](../Topic/Method%20Parameters%20\(C%23%20Reference\).md) dürfen keine Standardwerte besitzen. Verwenden Sie Methodenüberladungen, wenn Sie denselben Effekt erzielen möchten. Weitere Informationen finden Sie unter [Übergeben von Parametern](../Topic/Passing%20Parameters%20\(C%23%20Programming%20Guide\).md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS0241 generiert: Darüber hinaus veranschaulicht das Beispiel mithilfe der Überladung das Simulieren einer Methode mit Standardargumenten.  
  
```  
// CS0241.cs public class A { public void Test(int i = 9) {}   // CS0241 } public class B { public void Test() { Test(9); } public void Test(int i)  {} } public class C { public static void Main() { B x = new B(); x.Test(); } }  
```