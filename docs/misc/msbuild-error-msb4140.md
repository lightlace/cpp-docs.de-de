---
title: "MSBuild-Fehler MSB4140"
ms.custom: na
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "MSB4140"
ms.assetid: 13546558-4ed4-44c2-89a6-f69a2b43ed07
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "douge"
---
# MSBuild-Fehler MSB4140
**MSB4140: Die Standardtoolsversion ist weder in der Registrierung noch in der Konfigurationsdatei angegeben.**  
  
 Im Projekt ist kein standardmäßiger `ToolsVersion`\-Wert angegeben.  Daher weiß [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] nicht, welcher Wert verwendet werden soll.  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass ein `DefaultToolsVersion`\-Wert entweder in der Registrierung, in der Toolsets definiert sind, oder in einer Konfigurationsdatei \(wie z. B. msbuild.exe.config\) angegeben ist.  
  
## Siehe auch  
 [Standard and Custom Toolset Configurations](../Topic/Standard%20and%20Custom%20Toolset%20Configurations.md)   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [Additional Resources](../Topic/Additional%20MSBuild%20Resources.md)