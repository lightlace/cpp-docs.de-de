---
title: "Compilerfehler CS0715"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0715"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0715"
ms.assetid: e3cd1e46-ccfa-4678-a2ed-69245f3558ba
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0715
'Statische Klasse': Statische Klassen können keine benutzerdefinierten Operatoren enthalten.  
  
 Benutzerdefinierte Operatoren verwenden Instanzen von Klassen. Statische Klassen können nicht instanziiert werden, daher ist es nicht möglich, Instanzen für Operatoren zu erstellen, auf die reagiert werden kann. Daher sind benutzerdefinierte Operatoren für statische Klassen nicht zulässig.  
  
 Im folgenden Beispiel wird CS0715 generiert:  
  
```  
// CS0715.cs public static class C { public static C operator+(C c)  // CS0715 { } public static void Main() { } }  
```