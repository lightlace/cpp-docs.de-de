---
title: "MSBuild Error MSB1019"
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
  - "MSBuild.InvalidLoggerError"
helpviewer_keywords: 
  - "MSB1019"
ms.assetid: 5d0169f7-f878-433a-ac30-d9d6010130af
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1019
**Der Protokollierungsschalter wurde nicht richtig formuliert.**  
  
 Der Schalter **\/logger** ist nicht ordnungsgemäß angegeben.  Zum Angeben einer Protokollierung müssen Sie mindestens die Protokollierungsassembly angeben. Wenn Sie explizit die zu ladende Protokollierung angeben möchten, müssen Sie neben der Protokollierungsassembly auch die Protokollierungsklasse angeben.  Protokollierungsparameter sind optional.  
  
### So beheben Sie diesen Fehler  
  
1.  Geben Sie sowohl unter Verwendung der Protokollierungsklasse als auch der Protokollierungsassembly eine Protokollierung an.  Die `<logger>`\-Syntax lautet:  
  
     `<logger class>,<logger assembly>[;<logger parameters>]`  
  
     Die `<logger class>`\-Syntax lautet:  
  
    ```  
    [<partial or full namespace>.]<logger class name>  
    ```  
  
     Die `<logger assembly>`\-Syntax lautet:  
  
    ```  
    {<assembly name>[,<strong name>] | <assembly file>}  
    ```  
  
     `<logger parameters>` sind optional und werden so an die Protokollierung übergeben, wie sie eingegeben wurden.  
  
     Beispiel: \/`logger:XMLLogger,MyLogger,Version=1.0.2,Culture=neutral`  
  
## Siehe auch  
 [Command\-Line Reference](../Topic/MSBuild%20Command-Line%20Reference.md)   
 [Build Loggers](../Topic/Build%20Loggers.md)