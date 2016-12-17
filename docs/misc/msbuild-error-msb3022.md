---
title: "MSBuild Error MSB3022"
ms.custom: na
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MSBuild.Copy.ExactlyOneTypeOfDestination"
helpviewer_keywords: 
  - "MSB3022"
ms.assetid: 74ebcced-8a56-4502-8fef-43d36c79a640
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3022
**Sowohl \<Attribut\> als auch \<Attribut\> waren als Eingabeparameter in der Projektdatei angegeben.  Wählen Sie nur einen der Parameter aus.**  
  
 Für die `Copy`\-Aufgabe müssen Sie `DestinationFiles` oder `DestinationDirectory` angeben, aber nicht beide Aufgabenattribute.  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie `DestinationFiles` oder `DestinationDirectory` für die `Copy`\-Aufgabe in der Projektdatei an.  
  
## Siehe auch  
 [Copy Task](../Topic/Copy%20Task.md)   
 [Tasks](../Topic/MSBuild%20Tasks.md)