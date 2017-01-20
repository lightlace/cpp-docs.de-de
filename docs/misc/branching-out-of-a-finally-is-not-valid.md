---
title: "Verzweigungen aus einem &quot;Finally&quot; sind ung&#252;ltig."
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
  - "bc30101"
  - "vbc30101"
helpviewer_keywords: 
  - "BC30101"
ms.assetid: 16a0dc29-3657-4373-b77f-38f3cb80e6c9
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Verzweigungen aus einem &quot;Finally&quot; sind ung&#252;ltig.
Eine `GoTo`\-Anweisung in einem `Finally`\-Block bewirkt einen Sprung aus dem Block. Es ist nicht zulässig, in einen oder aus einem `Catch`\- oder `Finally`\-Block zu springen.  
  
 **Fehler\-ID:** BC30101  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die `GoTo`\-Anweisung, und implementieren Sie die Programmlogik mit Entscheidungs\- oder Schleifensteuerungsstrukturen.  
  
## Siehe auch  
 [Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md)   
 [GoTo Statement](../Topic/GoTo%20Statement.md)   
 [Control Flow](../Topic/Control%20Flow%20in%20Visual%20Basic.md)