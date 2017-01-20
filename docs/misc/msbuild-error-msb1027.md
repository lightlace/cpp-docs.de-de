---
title: "MSBuild Error MSB1027"
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
  - "MSBuild.CannotAutoDisableAutoResponseFile"
helpviewer_keywords: 
  - "MSB1027"
ms.assetid: 2ef8d643-616c-4608-be76-5c2c8e18a9e7
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1027
**Der Schalter \/noautoresponse kann weder in der automatischen Antwortdatei MSBuild.rsp noch in einer anderen Antwortdatei, auf die die automatische Antwortdatei verweist, verwendet werden.**  
  
 In der Datei MSBuild.rsp oder einer anderen darin enthaltenen Antwortdatei wurde der Schalter **\/noautoresponse** gefunden.  Die automatische Antwortdatei kann nicht dazu verwendet werden, sich selbst auszuschalten.  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie eine andere Antwortdatei an.  
  
-   Entfernen Sie den Schalter **\/noautoresponse** aus der Antwortdatei MSBuild.rsp.  
  
## Siehe auch  
 [Command\-Line Reference](../Topic/MSBuild%20Command-Line%20Reference.md)