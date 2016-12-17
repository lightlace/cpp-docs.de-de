---
title: "&quot;Global&quot; ist in Handles nicht zul&#228;ssig. Es wird ein lokaler Name erwartet."
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
  - "bc36002"
  - "vbc36002"
helpviewer_keywords: 
  - "BC36002"
ms.assetid: 7b4602a9-84c9-4068-81bc-e8df03ffc130
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Global&quot; ist in Handles nicht zul&#228;ssig. Es wird ein lokaler Name erwartet.
Eine `Handles`\-Klausel muss auf ein lokales Ereignis verweisen. Das `Global`\-Schlüsselwort ermöglicht den Zugriff auf globale Programmierelemente.  
  
 **Fehler\-ID:** BC36002  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie die `Handles`\-Klausel so, dass sie auf eine lokale Instanz des Ereignisses statt auf die globale Instanz verweist.  
  
## Siehe auch  
 [Global \- delete](assetId:///18c8ba14-40f6-4978-8096-6a5852324635)   
 [Handles](../Topic/Handles%20Clause%20\(Visual%20Basic\).md)   
 [Events](../Topic/Events%20\(Visual%20Basic\).md)