---
title: "Der Typparameter &lt;Typparametername&gt; hat denselben Namen wie der Typparameter eines einschlie&#223;enden Typs."
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
  - "vbc40048"
  - "bc40048"
helpviewer_keywords: 
  - "BC40048"
ms.assetid: d5428b36-88d3-42c4-a096-cbc7bb9571f2
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Der Typparameter &lt;Typparametername&gt; hat denselben Namen wie der Typparameter eines einschlie&#223;enden Typs.
Ein Typparameter eines generischen Typs wird mit dem gleichen Namen wie ein Typparameter eines enthaltenden generischen Typs deklariert.  
  
 In der Typparameterliste eines generischen Typs muss sich jeder Typparameternamen von den folgenden Namen unterscheiden:  
  
-   Von den Namen aller anderen Typparameter in derselben Typparameterliste,  
  
-   Von den Namen aller Typparameter in der Typparameterliste jedes enthaltenden generischen Typs und  
  
-   Vom Namen des generischen Typparameters selbst.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC40048  
  
### So beheben Sie diesen Fehler  
  
-   Benennen Sie den Typparameter so um, dass sein Name keinem in der Liste auf dieser Hilfeseite angegebenen Namen entspricht.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)