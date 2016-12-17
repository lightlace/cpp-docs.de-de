---
title: "MSBuild Error MSB1024"
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
  - "MSBuild.MultipleSchemasError"
helpviewer_keywords: 
  - "MSB1024"
ms.assetid: dff30870-da1a-479f-998b-03d0f5e16088
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1024
**Es darf nur ein Schema für die Validierung des Projekts angegeben werden.**  
  
 Nur ein Schema darf für den Schalter **\/validate** angegeben werden.  
  
### So beheben Sie diesen Fehler  
  
1.  Geben Sie unter Verwendung des Formats `/validate:<schema>` nur ein Schema für die Validierung des Projekts an, z. B. `/validate:MyExtendedBuildSchema.xsd`.  
  
## Siehe auch  
 [Command\-Line Reference](../Topic/MSBuild%20Command-Line%20Reference.md)