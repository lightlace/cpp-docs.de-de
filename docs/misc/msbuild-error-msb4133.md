---
title: "MSBuild Error MSB4133"
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
  - "MSB4133"
ms.assetid: 5f18937a-fda1-4315-81f9-7cee02802a6d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB4133
**MSB4133: Eine Standardtoolsversion "\<x.x.\>" wurde angegeben, aber ihre Definition konnte nicht gefunden werden.**  
  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] kann das Toolset nicht finden, das in der Projektdatei als `DefaultToolsVersion` definiert ist.  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass `DefaultToolsVersion` richtig angegeben ist und dass dieses Toolset entweder in der Registrierung oder in der [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]\-Konfigurationsdatei definiert ist.  
  
## Siehe auch  
 <xref:Microsoft.Build.BuildEngine.Toolset>   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [Additional Resources](../Topic/Additional%20MSBuild%20Resources.md)