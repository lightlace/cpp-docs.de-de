---
title: "&#39;Spezifizierer&#39; ist in einer Schnittstellenereignisdeklaration ung&#252;ltig."
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
  - "bc30275"
  - "vbc30275"
helpviewer_keywords: 
  - "BC30275"
ms.assetid: bd12c952-c619-4753-8d6d-90ef4086fdc2
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Spezifizierer&#39; ist in einer Schnittstellenereignisdeklaration ung&#252;ltig.
Eine `Event`\-Anweisung innerhalb einer Schnittstelle enthält ein unzulässiges Schlüsselwort, z. B. `Implements`. Eine Schnittstelle kann Member nur definieren, nicht implementieren.  
  
 **Fehler\-ID:** BC30275  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie das Schlüsselwort aus der Deklarationsanweisung.  
  
2.  Lagern Sie die Implementierung der Schnittstellenmember in eine Klasse aus, die die Schnittstelle implementiert.  
  
## Siehe auch  
 [Interface Statement](../Topic/Interface%20Statement%20\(Visual%20Basic\).md)   
 [Implements Statement](../Topic/Implements%20Statement.md)