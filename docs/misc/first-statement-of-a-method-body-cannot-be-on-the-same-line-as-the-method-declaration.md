---
title: "Die erste Anweisung eines Methodentexts darf sich nicht auf derselben Zeile wie die Methodendeklaration befinden."
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
  - "vbc30040"
  - "bc30040"
helpviewer_keywords: 
  - "BC30040"
ms.assetid: 27df3488-de77-499d-b9a6-08037d540cb0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Die erste Anweisung eines Methodentexts darf sich nicht auf derselben Zeile wie die Methodendeklaration befinden.
Eine `Function`\-, `Sub`\-, `Get`\-, `Set`\- oder `Property`\-Anweisung muss sich allein in einer Quellcodezeile befinden.  
  
 **Fehler\-ID:** BC30040  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie alle Zeilenbezeichnungen vor der Deklaration der Prozedur.  
  
2.  Verschieben Sie alle Anweisungen vor der Deklaration der Prozedur in eine vorherige Quellcodezeile.  
  
3.  Verschieben Sie alle Anweisungen nach der Deklaration der Prozedur in eine nachfolgende Quellcodezeile.  
  
## Siehe auch  
 [Procedures](../Topic/Procedures%20in%20Visual%20Basic.md)   
 [How to: Label Statements](../Topic/How%20to:%20Label%20Statements%20\(Visual%20Basic\).md)