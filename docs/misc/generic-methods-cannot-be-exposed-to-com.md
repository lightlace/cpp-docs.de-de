---
title: "Generische Methoden k&#246;nnen nicht f&#252;r COM verf&#252;gbar gemacht werden."
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30943"
  - "bc30943"
helpviewer_keywords: 
  - "BC30943"
ms.assetid: 0e3bff62-f187-4864-8520-70f6be22e869
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Generische Methoden k&#246;nnen nicht f&#252;r COM verf&#252;gbar gemacht werden.
Eine [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)]\-Komponente, die eine oder mehrere generische Prozeduren enthält, wird in eine COM\-Komponente exportiert.  
  
 Das Component Object Model \(COM\) unterstützt keine generische Typen und kann nicht mit ihnen zusammenarbeiten.  
  
 **Fehler\-ID:** BC30943  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die generischen Prozeduren aus der [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)]\-Komponente, oder verwenden Sie sie nicht für COM\-Interop.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [COM Interop](../Topic/COM%20Interop%20\(Visual%20Basic\).md)