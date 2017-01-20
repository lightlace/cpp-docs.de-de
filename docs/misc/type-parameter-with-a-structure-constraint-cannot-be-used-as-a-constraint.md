---
title: "Ein Typparameter mit einer Structure-Einschr&#228;nkung kann nicht als Einschr&#228;nkung verwendet werden."
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
  - "vbc32114"
  - "bc32114"
helpviewer_keywords: 
  - "BC32114"
ms.assetid: 442b2048-9dc4-4223-bcfc-4d96bf8d14de
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Ein Typparameter mit einer Structure-Einschr&#228;nkung kann nicht als Einschr&#228;nkung verwendet werden.
Ein Typparameter mit einer `Structure`\-Einschränkung wird als Einschränkung für einen anderen Typparameter verwendet.  
  
 Die `Structure`\-Einschränkung setzt voraus, dass das an den Typparameter übergebene Typargument ein Werttyp ist. Allerdings kann ein Werttyp nicht implementiert oder geerbt werden. Daher es nicht sinnvoll, ihn als Einschränkung zu verwenden, da der andere Typparameter ihn implementieren oder erben müsste.  
  
 Diese Situation ergibt nur dann einen Sinn, wenn beide Typargumente genau denselben Typ aufweisen müssen. In diesem Fall braucht der generische Typ nur ein Typparameter zu sein.  
  
 Dieser Fehler kann durch die folgende Anweisung generiert werden.  
  
 `Class c1(Of t1 As Structure, t2 As t1)`  
  
 Der an `t2` übergebene Typ kann den an `t1` übergebenen Typ nicht implementieren oder erben, da der an `t1` übergebene Typ ein Werttyp sein muss.  
  
 **Fehler\-ID:** BC32114  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie den mit `Structure` eingeschränkten Typparameter aus der Einschränkungsliste des anderen Typparameters.  
  
-   Wenn beide Typparameter denselben Werttyp erfordern, definieren Sie den generischen Typ mit nur einem Typparameter.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)   
 [Structure \(Visual Basic\)](assetId:///263ce115-ac36-4c05-8cb7-0e0eead5c6d0)   
 [Value Types and Reference Types](../Topic/Value%20Types%20and%20Reference%20Types.md)