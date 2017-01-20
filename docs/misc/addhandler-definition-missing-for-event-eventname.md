---
title: "Die AddHandler-Definition fehlt f&#252;r das &quot;&lt;Ereignisname&gt;&quot;-Ereignis."
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
  - "bc31130"
  - "vbc31130"
helpviewer_keywords: 
  - "BC31130"
ms.assetid: cf6c7fd6-ce2e-4916-b427-2a4a63e7279d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Die AddHandler-Definition fehlt f&#252;r das &quot;&lt;Ereignisname&gt;&quot;-Ereignis.
Wenn ein Ereignis als `Custom` deklariert wird, müssen sie ein Verfahren zum Hinzufügen eines Ereignishandlers bereitstellen.  
  
 **Fehler\-ID:** BC31130  
  
### So beheben Sie diesen Fehler  
  
1.  Fügen Sie eine `AddHandler`\-Deklaration zwischen der `Custom Event`\-Anweisung und der `End Event`\-Anweisung ein.  
  
2.  Stellen Sie sicher, dass andere Prozeduren innerhalb der Ereignisdeklaration korrekt beendet werden.  
  
## Siehe auch  
 [AddHandler Statement](../Topic/AddHandler%20Statement.md)   
 [Event Statement](../Topic/Event%20Statement.md)