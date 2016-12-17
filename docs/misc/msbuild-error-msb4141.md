---
title: "MSBuild-Fehler MSB4141"
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
  - "MSB4141"
ms.assetid: 0d190884-e64d-4d6b-817d-ce4644788fce
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "douge"
---
# MSBuild-Fehler MSB4141
**MSB4141: MSBuildToolsPath ist für die ToolsVersion "\<x.x\>" nicht angegeben.**  
  
 Ein benutzerdefiniertes Toolset ist definiert, es ist jedoch kein Wert für `MSBuildToolsPath` angegeben.  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie beim Definieren eines benutzerdefinierten Toolsets in der Registrierung oder der [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]\-Konfigurationsdatei einen gültigen Wert für `MSBuildToolsPath` an.  
  
## Siehe auch  
 [Standard and Custom Toolset Configurations](../Topic/Standard%20and%20Custom%20Toolset%20Configurations.md)   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [Additional Resources](../Topic/Additional%20MSBuild%20Resources.md)