---
title: "Der Typparameter wurde bereits mit dem Namen &lt;Typparametername&gt; deklariert."
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
  - "vbc32049"
  - "bc32049"
helpviewer_keywords: 
  - "BC32049"
ms.assetid: d7affad0-0c3d-4fce-a1c2-a17f65514471
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Der Typparameter wurde bereits mit dem Namen &lt;Typparametername&gt; deklariert.
Ein Typparameter eines generischen Typs wird mit dem gleichen Namen wie ein anderer Typparameter desselben generischen Typs deklariert.  
  
 In der Typparameterliste eines generischen Typs muss sich jeder Typparameternamen von den folgenden Namen unterscheiden:  
  
-   Von den Namen aller anderen Typparameter in derselben Typparameterliste,  
  
-   Von den Namen aller Typparameter in der Typparameterliste jedes enthaltenden generischen Typs und  
  
-   Vom Namen des generischen Typparameters selbst.  
  
 **Fehler\-ID:** BC32049  
  
### So beheben Sie diesen Fehler  
  
-   Benennen Sie den Typparameter so um, dass sein Name keinem in der Liste auf dieser Hilfeseite angegebenen Namen entspricht.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)