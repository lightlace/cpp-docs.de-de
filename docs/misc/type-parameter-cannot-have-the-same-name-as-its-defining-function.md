---
title: "Ein Typparameter kann nicht den gleichen Namen haben wie die ihn definierende Funktion."
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
  - "vbc32090"
  - "bc32090"
helpviewer_keywords: 
  - "BC32090"
ms.assetid: 02f4d82c-dcd7-44cc-b725-81e235f680f6
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Ein Typparameter kann nicht den gleichen Namen haben wie die ihn definierende Funktion.
Ein Typparameter eines generischen Typs wird mit dem gleichen Namen wie der generische Typ deklariert.  
  
 In der Typparameterliste eines generischen Typs muss sich jeder Typparametername von den folgenden Namen unterscheiden:  
  
-   von den Namen aller anderen Typparameter in derselben Typparameterliste,  
  
-   von den Namen aller Typparameter in der Typparameterliste jedes enthaltenden generischen Typs und  
  
-   vom Namen des generischen Typs selbst.  
  
 **Fehler\-ID:** BC32090  
  
### So beheben Sie diesen Fehler  
  
-   Benennen Sie den Typparameter um, sodass sein Name keinem in der Liste auf dieser Hilfeseite angegebenen Namen entspricht.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)