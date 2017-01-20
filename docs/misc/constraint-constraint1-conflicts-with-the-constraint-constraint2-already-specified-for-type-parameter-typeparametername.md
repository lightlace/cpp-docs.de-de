---
title: "Die Einschr&#228;nkung &#39;&lt;Einschr&#228;nkung1&gt;&#39; verursacht einen Konflikt mit der bereits f&#252;r den &#39;&lt;Typparametername&gt;&#39;-Typparameter angegebenen Einschr&#228;nkung &#39;&lt;Einschr&#228;nkung2&gt;&#39;."
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
  - "vbc32119"
  - "bc32119"
helpviewer_keywords: 
  - "BC32119"
ms.assetid: 30e6778d-5c2b-4f2d-a136-4e66fa9fbe4d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Die Einschr&#228;nkung &#39;&lt;Einschr&#228;nkung1&gt;&#39; verursacht einen Konflikt mit der bereits f&#252;r den &#39;&lt;Typparametername&gt;&#39;-Typparameter angegebenen Einschr&#228;nkung &#39;&lt;Einschr&#228;nkung2&gt;&#39;.
Ein generischer Typ wird mit in Konflikt stehenden Einschränkungen für einen Typparameter deklariert.  
  
 Dieser Fehler kann durch die folgende Anweisung generiert werden.  
  
 `Public Class testClass(Of t As {Structure, Class })`  
  
 Die Einschränkungen `Structure` und `Class` verursachen einen Konflikt für Typparameter `t`, weil die `Structure`\-Einschränkung erfordert, dass das entsprechende Typargument ein Werttyp ist, während `Class` erfordert, dass es ein Verweistyp ist.  
  
 **Fehler\-ID:** BC32119  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie die Typparametereinschränkungen, um Konflikte zu vermeiden.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)   
 [Structure \(Visual Basic\)](assetId:///263ce115-ac36-4c05-8cb7-0e0eead5c6d0)   
 [Class \(Visual Basic\)](assetId:///0777c6e6-46bc-451b-ad70-57b49d4ef4f7)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)