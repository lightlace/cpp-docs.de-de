---
title: "Typ &quot;&lt;Typname&gt;&quot; kann nicht von einem Typparameter erben."
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc32055"
  - "vbc32055"
helpviewer_keywords: 
  - "BC32055"
ms.assetid: 97af7cad-6e40-41e3-892d-1fbcbd86356d
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "shoag"
manager: "wpickett"
---
# Typ &quot;&lt;Typname&gt;&quot; kann nicht von einem Typparameter erben.
Eine Klasse oder Schnittstelle enthält eine [Inherits Statement](../Topic/Inherits%20Statement.md), die einen generischen Typparameter angibt.  
  
 Ein Typ kann nicht von einem Typ erben, der noch nicht definiert wurde. Ein Merkmal von Vererbung ist die Fähigkeit, Member der Basisklasse wiederzuverwenden. Dies setzt wiederum voraus, dass diese Member definiert sind. Ein generischer Typparameter ist ein Platzhalter, der durch einen bestimmten, von einem Typargument bereitgestellten Typ ersetzt werden muss. Folglich kann ein Typ nicht vom Platzhalter erben.  
  
 **Fehler\-ID:** BC32055  
  
### So beheben Sie diesen Fehler  
  
-   Wenn der erbende Typ von einem anderen Typ erben muss, verwenden Sie anstelle eines Typparameters einen spezifischen Typ.  
  
-   Wenn der Basistyp durch einen generischen Typparameter dargestellt werden muss, kann kein anderer Typ von ihm erben. Entfernen Sie die [Inherits Statement](../Topic/Inherits%20Statement.md).  
  
## Siehe auch  
 [NICHT IM BUILD: Vererbung in Visual Basic](assetId:///e5e6e240-ed31-4657-820c-079b7c79313c)   
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)