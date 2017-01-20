---
title: "Eine Return-Anweisung in „Sub“ oder „Set“ kann keinen Wert zur&#252;ckgeben."
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
  - "bc30647"
  - "vbc30647"
helpviewer_keywords: 
  - "BC30647"
ms.assetid: d4c05c28-d650-4f49-976e-650d84802036
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Eine Return-Anweisung in „Sub“ oder „Set“ kann keinen Wert zur&#252;ckgeben.
`Sub`\-Prozeduren und `Set`\-Eigenschaftenprozeduren können keine Werte zurückgeben.  
  
 **Fehler\-ID:** BC30647  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie die aktuelle Prozedur in eine Funktion oder eine `Get`\-Eigenschaftenprozedur, wenn die aktuelle Prozedur Teil einer Eigenschaft ist.  
  
-   Sie können Werte von `Sub`\-Prozeduren effektiv zurückgeben, indem Sie die Werte von Parametern ändern, die mithilfe eines Verweises mit dem `ByRef`\-Schlüsselwort übergeben wurden.  
  
## Siehe auch  
 [Return Statement](../Topic/Return%20Statement%20\(Visual%20Basic\).md)   
 [Sub Procedures](../Topic/Sub%20Procedures%20\(Visual%20Basic\).md)   
 [Function\-Prozeduren](../Topic/Function%20Procedures%20\(Visual%20Basic\).md)   
 [Eigenschaftenprozeduren](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)