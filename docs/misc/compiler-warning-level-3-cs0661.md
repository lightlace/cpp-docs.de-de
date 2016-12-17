---
title: "Compilerwarnung (Stufe 3) CS0661"
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
  - "CS0661"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0661"
ms.assetid: c218665e-5947-40bb-b633-d268483e6522
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerwarnung (Stufe 3) CS0661
'Klasse' definiert den Operator \=\= oder \!\=, aber überschreibt Object.GetHashCode\(\) nicht.  
  
 Der Compiler hat den benutzerdefinierten Gleichheits\- oder Ungleichheitsoperator, aber keine Überschreibung für die **GetHashCode**\-Funktion erkannt. Ein benutzerdefinierte Gleichheits\- oder Ungleichheitsoperator impliziert, dass Sie auch die **GetHashCode**\-Funktion überschreiben möchten.  
  
 Im folgenden Beispiel wird CS0661 generiert:  
  
```  
// CS0661.cs // compile with: /W:3 class Test   // CS0661 { public static bool operator == (object o, Test t) { return true; } public static bool operator != (object o, Test t) { return true; } public override bool Equals(object o) { return true; } // uncomment the GetHashCode function to resolve // public override int GetHashCode() // { //    return 0; // } public static void Main() { } }  
```