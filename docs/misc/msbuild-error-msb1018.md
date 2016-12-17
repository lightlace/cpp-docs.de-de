---
title: "MSBuild Error MSB1018"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MSBuild.InvalidVerbosityError"
helpviewer_keywords: 
  - "MSB1018"
ms.assetid: fb4deacc-a799-44e8-8980-d70d9da4caa1
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1018
**Der Ausführlichkeitsgrad ist ungültig.**  
  
 Der angegebene Ausführlichkeitsgrad entspricht keinem der verfügbaren Ausführlichkeitsgrade.  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die Rechtschreibung des Ausführlichkeitsgrads.  Die verfügbaren Ausführlichkeitsgrade sind: q\[uiet\], m\[inimal\], n\[ormal\], d\[etailed\] und diag\[nostic\], z. B. `/verbosity:quiet`,  `/verbosity:q` oder  `/v:q`.  
  
## Siehe auch  
 [Command\-Line Reference](../Topic/MSBuild%20Command-Line%20Reference.md)   
 [Build Loggers](../Topic/Build%20Loggers.md)