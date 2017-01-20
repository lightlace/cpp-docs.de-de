---
title: "Die End-Anweisung kann nicht in Klassenbibliothekprojekten verwendet werden"
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
  - "bc30615"
  - "vbc30615"
helpviewer_keywords: 
  - "BC30615"
ms.assetid: c8606b17-b50b-4014-b76e-b748d57e9389
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Die End-Anweisung kann nicht in Klassenbibliothekprojekten verwendet werden
In zum Erstellen von DLLs verwendeten Klassenbibliothekprojekten ist die Verwendung des `End`\-Schlüsselworts zum Beenden der Codeausführung in einer Prozedur unzulässig.  
  
 **Fehler\-ID:** BC30615  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie Steuerungsstrukturen wie `While` und `For`, um den Ablauf der Programmausführung zu steuern.  
  
## Siehe auch  
 [Control Flow](../Topic/Control%20Flow%20in%20Visual%20Basic.md)