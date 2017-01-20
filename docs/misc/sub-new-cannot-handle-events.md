---
title: "&#39;Sub New&#39; kann keine Ereignisse behandeln."
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
  - "vbc30497"
  - "bc30497"
helpviewer_keywords: 
  - "BC30497"
ms.assetid: b8a546c4-914e-49de-b553-9fc0f41424ed
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Sub New&#39; kann keine Ereignisse behandeln.
Sie haben versucht, `Sub New` mit `Handles` zu kombinieren. Dies ist ungültig. Verwenden Sie das `Handles`\-Schlüsselwort am Ende der Prozedurdeklaration, damit sie Ereignisse verarbeitet, die durch eine mithilfe des Schlüsselworts `WithEvents` deklarierte Objektvariable ausgelöst wurden.  
  
 **Fehler\-ID:** BC30497  
  
### So beheben Sie diesen Fehler  
  
1.  Verwenden Sie in diesem Kontext nicht `New`.  
  
## Siehe auch  
 [Handles](../Topic/Handles%20Clause%20\(Visual%20Basic\).md)   
 [Dim Statement](../Topic/Dim%20Statement%20\(Visual%20Basic\).md)   
 [WithEvents](../Topic/WithEvents%20\(Visual%20Basic\).md)