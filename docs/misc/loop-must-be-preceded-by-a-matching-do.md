---
title: "&quot;Loop&quot; muss ein entsprechendes &quot;Do&quot; voranstehen."
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
  - "vbc30091"
  - "bc30091"
helpviewer_keywords: 
  - "BC30091"
ms.assetid: 05f47b2f-4eaa-4911-981e-3fce737d249f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;Loop&quot; muss ein entsprechendes &quot;Do&quot; voranstehen.
Eine `Loop`\-Anweisung tritt ohne entsprechende `Do`\-Anweisung auf.`Loop` muss eine entsprechende `Do`\-Anweisung vorangestellt sein.  
  
 **Fehler\-ID:** BC30091  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn diese `Do`\-Schleife Teil einer Reihe von geschachtelten `Do`\-Schleifen ist, stellen Sie sicher, dass jede Schleife ordnungsgemäß abgeschlossen wird.  
  
2.  Stellen Sie sicher, dass andere Steuerungsstrukturen innerhalb der `Do`\-Schleife ordnungsgemäß abgeschlossen werden.  
  
3.  Stellen Sie sicher, dass diese `Do`\-Schleife ordnungsgemäß formatiert ist.  
  
## Siehe auch  
 [Do...Loop Statement](../Topic/Do...Loop%20Statement%20\(Visual%20Basic\).md)