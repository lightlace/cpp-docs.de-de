---
title: "Module k&#246;nnen nicht generisch sein."
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
  - "BC32073"
  - "vbc32073"
helpviewer_keywords: 
  - "BC32073"
ms.assetid: 47246e2b-51d4-4a10-a3ac-bc77b44fa2ca
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Module k&#246;nnen nicht generisch sein.
Ein `Module`\-Anweisung verwendet das `Of`\-Schlüsselwort, um generische Typparameter einzuführen.  
  
 Sie können generische Klassen, Strukturen, Schnittstellen, Prozeduren und Delegaten definieren und verwenden. Sie können jedoch keine generischen Module definieren.  
  
 **Fehler\-ID:** BC32073  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie das `Of`\-Schlüsselwort aus der `Module`\-Anweisung.  
  
2.  Wenn Sie die Funktionalität eines generischen Moduls benötigen, entspricht diesem am ehesten eine generische Klasse. Verwenden Sie eine [Class Statement](../Topic/Class%20Statement%20\(Visual%20Basic\).md) statt einer `Module`\-Anweisung.  
  
## Siehe auch  
 [Module Statement](../Topic/Module%20Statement.md)   
 [Of](../Topic/Of%20Clause%20\(Visual%20Basic\).md)   
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Gewusst wie: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann](../Topic/How%20to:%20Define%20a%20Class%20That%20Can%20Provide%20Identical%20Functionality%20on%20Different%20Data%20Types%20\(Visual%20Basic\).md)