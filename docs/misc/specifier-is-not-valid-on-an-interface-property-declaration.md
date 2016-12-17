---
title: "&#39;&lt;Spezifizierer&gt;&#39; ist in einer Schnittstellen-Eigenschaftendeklaration ung&#252;ltig."
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
  - "vbc30273"
  - "bc30273"
helpviewer_keywords: 
  - "BC30273"
ms.assetid: f10c4f5f-6176-4dba-99a9-b58f3b390fba
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;Spezifizierer&gt;&#39; ist in einer Schnittstellen-Eigenschaftendeklaration ung&#252;ltig.
Eine `Property`\-Anweisung innerhalb einer Schnittstelle enthält ein ungültiges Schlüsselwort, z. B. `Implements`. Eine Schnittstelle kann Member nur definieren, nicht implementieren.  
  
 **Fehler\-ID:** BC30273  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das ungültige Schlüsselwort aus der Deklarationsanweisung.  
  
-   Lagern Sie die Implementierung der Schnittstellenmember in eine Klasse aus, die die Schnittstelle implementiert.  
  
## Siehe auch  
 [Interface Statement](../Topic/Interface%20Statement%20\(Visual%20Basic\).md)   
 [Implements Statement](../Topic/Implements%20Statement.md)