---
title: "MSBuild Error MSB1002"
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
  - "MSBuild.UnexpectedParametersError"
helpviewer_keywords: 
  - "MSB1002"
ms.assetid: 798c9690-6d99-4f21-a491-ab44d3f3c552
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1002
**Der Schalter erlaubt keine Parameter.**  
  
 Für diesen Schalter können keine Parameter definiert werden.  Nur der Name des Schalters ist erforderlich, und ihm darf kein Doppelpunkt folgen.  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie den Befehl ohne Parameter für diesen Schalter ein. Anstelle von `msbuild /<switch>:<parameters>` geben Sie also `msbuild /<switch>` ein.  
  
-   Entfernen Sie den Doppelpunkt nach dem Schalternahmen. Anstelle von `msbuild /<switch>:` geben Sie also `msbuild /<switch>` ein.  
  
## Siehe auch  
 [Command\-Line Reference](../Topic/MSBuild%20Command-Line%20Reference.md)