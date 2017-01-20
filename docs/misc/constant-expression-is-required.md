---
title: "Konstanter Ausdruck erforderlich."
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
  - "bc30059"
  - "vbc30059"
helpviewer_keywords: 
  - "BC30059"
ms.assetid: fdd5e7bb-6370-4a63-bbb6-23b15badb4c8
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# Konstanter Ausdruck erforderlich.
Eine `Const`\-Anweisung initialisiert eine Konstante nicht ordnungsgemäß, oder eine Arraydeklaration verwendet eine Variable, um die Anzahl der Elemente anzugeben.  
  
 **Fehler\-ID:** BC30059  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn die Deklaration eine `Const`\-Anweisung ist, überprüfen Sie, ob die Konstante mit einem Literal, einer zuvor deklarierten Konstante, einem Enumerationsmember oder einer Kombination aus Literalen, Konstanten und Enumerationsmembern initialisiert wird, die mit Operatoren kombiniert werden.  
  
2.  Wenn die Deklaration ein Array angibt, überprüfen Sie, ob eine Variable verwendet wird, um die Anzahl der Elemente anzugeben. Wenn dies der Fall ist, ersetzen Sie die Variable durch einen konstanten Ausdruck.  
  
## Siehe auch  
 [Const Statement](../Topic/Const%20Statement%20\(Visual%20Basic\).md)   
 [NOTINBUILD: Arrayvariable](assetId:///c2da78bd-6928-46ba-805f-44f819dfaf93)