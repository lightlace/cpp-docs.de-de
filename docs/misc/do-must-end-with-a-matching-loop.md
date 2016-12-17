---
title: "&#39;Do&#39; muss mit einem entsprechenden &#39;Loop&#39; abgeschlossen werden."
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
  - "vbc30083"
  - "bc30083"
helpviewer_keywords: 
  - "BC30083"
ms.assetid: b157b9e3-57fa-4324-a13d-b37bcf0861e6
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Do&#39; muss mit einem entsprechenden &#39;Loop&#39; abgeschlossen werden.
Eine `Do`\-Anweisung tritt ohne eine entsprechende `Loop`\-Anweisung auf. Zum Beenden der `Do`\-Schleife muss eine `Loop`\-Anweisung angegeben werden.  
  
 **Fehler\-ID:** BC30083  
  
### So beheben Sie diesen Fehler  
  
-   Wenn diese `Do`\-Schleife Teil einer Reihe von geschachtelten Schleifen ist, stellen Sie sicher, dass jede Schleife ordnungsgemäß abgeschlossen wird.  
  
-   Fügen Sie eine `Loop`\-Anweisung ans Ende der `Do`\-Schleife hinzu.  
  
## Siehe auch  
 [Do...Loop Statement](../Topic/Do...Loop%20Statement%20\(Visual%20Basic\).md)