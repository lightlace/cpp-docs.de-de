---
title: "Keine Maus vorhanden"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbrMouse_NoMouseIsPresent"
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Keine Maus vorhanden
Eine der Eigenschaften des `My.Computer.Mouse`\-Objekts wurde aufgerufen, aber der Computer verfügt über keine Maus, oder es ist kein Port für die Maus installiert.  
  
### So beheben Sie diesen Fehler  
  
-   Fügen Sie rund um den Aufruf der Eigenschaft des `My.Computer.Mouse`\-Objekts einen `Try...Catch`\-Block hinzu.  
  
     Oder...  
  
-   Installieren Sie auf dem Computer eine Maus.  
  
## Siehe auch  
 [My.Computer.Mouse Object](../Topic/My.Computer.Mouse%20Object.md)   
 [Ausnahmen\- und Fehlerbehandlung in Visual Basic](assetId:///3e351e73-cf23-40ab-8b60-05794160529e)   
 [Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md)