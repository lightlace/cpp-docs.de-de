---
title: "MSBuild Error MSB1004"
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
  - "MSBuild.MissingTargetError"
helpviewer_keywords: 
  - "MSB1004"
ms.assetid: aed36761-ab07-486c-b5eb-48ccb1c387dd
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1004
**Geben Sie den Namen des Ziels an.**  
  
 Mindestens ein Ziel muss mit dem Schalter **\/target** angegeben werden.  
  
### So beheben Sie diesen Fehler  
  
1.  Geben Sie eines oder mehrere Ziele an.  Die Ziele in einer Liste können entweder durch ein Komma oder ein Semikolon voneinander getrennt werden, z. B. `/target:Clean;Compile`.  Alternativ können Sie den Schalter wiederholen, z. B. `/t:Clean /t:` `Compile`.  
  
## Siehe auch  
 [Targets](../Topic/MSBuild%20Targets.md)   
 [Command\-Line Reference](../Topic/MSBuild%20Command-Line%20Reference.md)