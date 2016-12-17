---
title: "Ein benanntes Argument kann nicht mit einem ParamArray-Parameter &#252;bereinstimmen"
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
  - "bc30587"
  - "vbc30587"
helpviewer_keywords: 
  - "BC30587"
ms.assetid: aff179af-96f2-4157-971e-881d8e08f5f2
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Ein benanntes Argument kann nicht mit einem ParamArray-Parameter &#252;bereinstimmen
Sie haben ein benanntes Argument angegeben \(mit dem deklarierten Namen des Arguments angegeben, gefolgt von einem Doppelpunkt und einem Gleichheitszeichen, gefolgt vom Argumentwert\); Parameterarrays können aber nicht anhand des Namens übergeben werden. Wenn Sie die Prozedur aufrufen, geben Sie eine unbegrenzte Anzahl von kommagetrennten Argumenten für das Parameterarray an, und der Compiler kann einem einzelnen Namen nicht mehr als ein Argument zuordnen.  
  
 **Fehler\-ID:** BC30587  
  
### So beheben Sie diesen Fehler  
  
-   Übergeben Sie das Argument anhand seiner Position statt über den Namen.  
  
## Siehe auch  
 [ParamArray](../Topic/ParamArray%20\(Visual%20Basic\).md)   
 [Passing Arguments by Position and by Name](../Topic/Passing%20Arguments%20by%20Position%20and%20by%20Name%20\(Visual%20Basic\).md)