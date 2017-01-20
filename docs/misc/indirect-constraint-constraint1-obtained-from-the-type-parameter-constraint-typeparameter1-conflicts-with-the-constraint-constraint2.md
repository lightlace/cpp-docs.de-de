---
title: "Die indirekte Einschr&#228;nkung &#39;&lt;einschr&#228;nkung1&gt;&#39;, die aus der Typparametereinschr&#228;nkung &#39;&lt;typparameter1&gt;&#39; abgerufen wurde, steht im Konflikt mit der Einschr&#228;nkung &#39;&lt;einschr&#228;nkung2&gt;&#39;"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc32111"
  - "vbc32111"
helpviewer_keywords: 
  - "BC32111"
ms.assetid: b03b5840-5318-4844-b2da-1bca4c28d097
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Die indirekte Einschr&#228;nkung &#39;&lt;einschr&#228;nkung1&gt;&#39;, die aus der Typparametereinschr&#228;nkung &#39;&lt;typparameter1&gt;&#39; abgerufen wurde, steht im Konflikt mit der Einschr&#228;nkung &#39;&lt;einschr&#228;nkung2&gt;&#39;
Ein generischer Typ wird aufgrund einer Kombination aus direkten und indirekten Einschränkungen mit im Konflikt stehenden Einschränkungen deklariert.  
  
 Dieser Fehler kann durch die folgende Anweisung generiert werden.  
  
 `Public Class testClass(Of t1 As {t2, Class}, t2 As Structure)`  
  
 Die indirekte Einschränkung `Structure` und die direkte Einschränkung `Class` verursachen einen Konflikt für Typparameter `t1`, weil die `Structure`\-Einschränkung erfordert, dass das entsprechende Typargument ein Werttyp ist, während `Class` erfordert, dass es ein Verweistyp ist.  
  
 **Fehler\-ID:** BC32111  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie die Typparametereinschränkungen, um einen Konflikt verursachende Einschränkungen zu vermeiden.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)   
 [Struktur \(Visual Basic\)](assetId:///263ce115-ac36-4c05-8cb7-0e0eead5c6d0)   
 [Class \(Visual Basic\)](assetId:///0777c6e6-46bc-451b-ad70-57b49d4ef4f7)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)