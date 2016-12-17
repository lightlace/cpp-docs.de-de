---
title: "„Next“ muss ein entsprechendes „For“ voranstehen."
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
  - "vbc30092"
  - "bc30092"
helpviewer_keywords: 
  - "BC30092"
ms.assetid: 4bf49bb2-c69b-443d-aa58-cb40fcfb1370
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# „Next“ muss ein entsprechendes „For“ voranstehen.
Eine `Next`\-Anweisung tritt ohne entsprechende `For`\- oder `For Each`\-Anweisung auf.`Next` muss eine entsprechende `For`\- oder `For Each`\-Anweisung vorangestellt sein.  
  
 **Fehler\-ID:** BC30092  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn diese `For`\-Schleife Teil einer Reihe von geschachtelten `For`\-Schleifen ist, stellen Sie sicher, dass jede Schleife korrekt abgeschlossen wird.  
  
2.  Stellen Sie sicher, dass andere Steuerungsstrukturen innerhalb der `For`\-Schleife ordnungsgemäß beendet werden.  
  
3.  Stellen Sie sicher, dass diese `For`\-Schleife korrekt formatiert ist.  
  
## Siehe auch  
 [For...Next\-Anweisung](../Topic/For...Next%20Statement%20\(Visual%20Basic\).md)   
 [For Each...Next\-Anweisung](../Topic/For%20Each...Next%20Statement%20\(Visual%20Basic\).md)