---
title: "Konvertierungsoperatoren k&#246;nnen keine Konvertierung eines Typs in den gleichen Typ durchf&#252;hren."
ms.custom: na
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc33024"
  - "vbc33024"
helpviewer_keywords: 
  - "BC33024"
ms.assetid: 4b47bcb0-4f0c-4d1c-9274-cce5b8e2b370
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Konvertierungsoperatoren k&#246;nnen keine Konvertierung eines Typs in den gleichen Typ durchf&#252;hren.
Ein Konvertierungsoperator wurde mit dem gleichen Typ für Parameter und Rückgabewert deklariert.  
  
 Es ist nicht sinnvoll, einen Typ in sich selbst zu konvertieren.  
  
 **Fehler\-ID:** BC33024  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie entweder den Typ des Parameters oder den Typ des Rückgabewerts. Einer der beiden Werte muss vom Typ der Klasse oder Struktur sein, in der dieser Operator definiert ist. Der andere muss einen anderen Typ aufweisen.  
  
-   Wenn Sie für den Inhalt des Parameters eine Transformation ausführen müssen, verwenden Sie eine [Function Statement](../Topic/Function%20Statement%20\(Visual%20Basic\).md) zum Definieren einer `Function`\-Prozedur anstelle eines Operators.  
  
## Siehe auch  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)