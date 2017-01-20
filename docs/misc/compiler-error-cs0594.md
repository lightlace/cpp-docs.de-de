---
title: "Compilerfehler CS0594"
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
  - "CS0594"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0594"
ms.assetid: a3d6bde1-db63-4c5c-a425-8c6a39e00999
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0594
Die Gleitkommakonstante liegt außerhalb des Bereichs von Typ "Typ".  
  
 Einer Gleitkommavariablen wurde ein Wert zugewiesen, der für die Variablen dieses Datentyps zu groß ist. Informationen zu dem für Datentypen zulässigen Wertebereich finden Sie in der [Tabelle ganzzahliger Typen](../Topic/Integral%20Types%20Table%20\(C%23%20Reference\).md).  
  
 Im folgenden Beispiel wird CS0594 generiert:  
  
```  
// CS0594.cs namespace MyNamespace { public class MyClass { public static void Main() { float f = 6.77777777777E400;   // CS0594, value too large } } }  
```