---
title: "Compilerfehler CS0262"
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
  - "CS0262"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0262"
ms.assetid: 44f8661f-c934-483f-84cd-00ca8257e50a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0262
Partielle Deklarationen von "Typ" haben Zugriffsmodifizierer, die miteinander in Konflikt stehen.  
  
 Dieser Fehler tritt auf, wenn ein partieller Typ über inkonsistente Modifizierer wie "public", "private", "protected", "internal" oder "abstract" verfügt. Diese Modifizierer müssen in allen partiellen Deklarationen für diesen Typ einheitlich sein. Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../Topic/Partial%20Classes%20and%20Methods%20\(C%23%20Programming%20Guide\).md).  
  
## Beispiel  
 Im folgenden Beispiel wird CS0262 generiert:  
  
```  
// CS0262.cs class A { public partial class C  // CS0262 { } private partial class C { } }  
```