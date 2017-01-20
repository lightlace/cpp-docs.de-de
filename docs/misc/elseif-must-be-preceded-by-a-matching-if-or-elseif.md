---
title: "&#39;ElseIf&#39; muss ein entsprechendes &#39;If&#39; oder &#39;ElseIf&#39; voranstehen."
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
  - "bc36005"
  - "vbc36005"
helpviewer_keywords: 
  - "BC36005"
ms.assetid: bcebae85-b438-4839-bada-2f8f8dcc8a86
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;ElseIf&#39; muss ein entsprechendes &#39;If&#39; oder &#39;ElseIf&#39; voranstehen.
Eine `ElseIf`\-Anweisung tritt ohne entsprechende `If`\-Anweisung auf.`ElseIf` eine `If`\- oder eine andere `ElseIf`\-Anweisung vorangestellt sein.  
  
 **Fehler\-ID:** BC36005  
  
### So beheben Sie diesen Fehler  
  
1.  Wenn dieser `If`\-Block Teil einer Reihe von geschachtelten Steuerungsstrukturen ist, stellen Sie sicher, dass jede Struktur ordnungsgemäß abgeschlossen wird.  
  
2.  Stellen Sie sicher, dass andere innerhalb des `If`\-Blocks geschachtelten Steuerungsstrukturen ordnungsgemäß beendet werden.  
  
3.  Stellen Sie sicher, dass dieser `If`\-Block ordnungsgemäß formatiert ist.  
  
## Siehe auch  
 [If...Then...Else Statement](../Topic/If...Then...Else%20Statement%20\(Visual%20Basic\).md)   
 [Decision Structures](../Topic/Decision%20Structures%20\(Visual%20Basic\).md)