---
title: "Compilerfehler CS0180"
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
  - "CS0180"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0180"
ms.assetid: a21bf0a2-ed5a-4ddd-88d3-240babc5888a
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0180
"Member" kann nicht gleichzeitig extern und abstrakt sein.  
  
 Die Schlüsselwörter [abstract](../Topic/abstract%20\(C%23%20Reference\).md) und [extern](../Topic/extern%20\(C%23%20Reference\).md) schließen sich gegenseitig aus. Das Schlüsselwort `extern` bedeutet, dass der Member außerhalb der Datei definiert ist. Das Schlüsselwort **abstract** bedeutet, dass die Implementierung in einer abgeleiteten Klasse bereitgestellt wird. Weitere Informationen finden Sie unter [Methoden](../Topic/Methods%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0180 generiert:  
  
```  
// CS0180.cs namespace MyNamespace { public class MyClass { public extern abstract int Foo(int a);   // CS0180 public static void Main() { } } }  
```