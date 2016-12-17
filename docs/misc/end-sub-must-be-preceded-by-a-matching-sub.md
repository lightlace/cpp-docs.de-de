---
title: "&quot;End Sub&quot; muss ein entsprechendes &quot;Sub&quot; voranstehen."
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
  - "vbc30429"
  - "bc30429"
helpviewer_keywords: 
  - "BC30429"
ms.assetid: cf9d0cfe-5dfa-4f6d-9d10-69eb16e413e1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;End Sub&quot; muss ein entsprechendes &quot;Sub&quot; voranstehen.
Im Code befindet sich eine `End Sub`\-Anweisung ohne entsprechende vorhergehende `Sub`\-Prozedurdefinition.  
  
 **Fehler\-ID:** BC30429  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die `End Sub`\-Anweisung, falls sie redundant ist.  
  
-   Geben Sie die fehlende `Sub`\-Prozedur ein, falls diese fehlt.  
  
-   Verschieben Sie `End Sub` an die entsprechende Stelle im Code.  
  
## Siehe auch  
 [Sub Procedures](../Topic/Sub%20Procedures%20\(Visual%20Basic\).md)   
 [End \<keyword\> Statement](../Topic/End%20%3Ckeyword%3E%20Statement%20\(Visual%20Basic\).md)