---
title: "Die Anweisung kann nicht innerhalb des Schnittstellentexts verwendet werden"
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
  - "vbc30603"
  - "BC30603"
helpviewer_keywords: 
  - "BC30603"
ms.assetid: 3aef29d6-eadf-4f1f-b214-dfeae5e51c4f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Die Anweisung kann nicht innerhalb des Schnittstellentexts verwendet werden
Die Deklaration eines Schnittstellenmembers enthält eine Anweisung zum Beenden des Members im Format `End` *Membername*.  
  
 Eine Schnittstelle definiert nur die Signatur ihrer Member. Daher weisen Prozeduren und Eigenschaften, die in einer Schnittstelle definiert sind, nur die erste Zeile mit Namen und Signatur auf. Sie fügen in die Schnittstelle keinen Code, interne Deklarationen oder eine `End Function`\-, eine `End Property`\- oder eine `End Sub`\-Anweisung ein.  
  
 **Fehler\-ID:** BC30603  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die `End` *Membername*\-Anweisung aus der Schnittstellendefinition.  
  
## Siehe auch  
 [Interface Statement](../Topic/Interface%20Statement%20\(Visual%20Basic\).md)   
 [End \<keyword\> Statement](../Topic/End%20%3Ckeyword%3E%20Statement%20\(Visual%20Basic\).md)