---
title: "MSBuild Error MSB4134"
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
  - "MSB4134"
ms.assetid: 2e4e6beb-c0c9-40ef-b75c-1c16244eba10
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB4134
**MSB4134: DefaultToolsVersion kann nicht festgelegt werden, nachdem ein Projekt in das Modul geladen wurde.**  
  
 Dieser Fehler tritt auf, wenn versucht wurde, den Wert von `DefaultToolsVersion` zu ändern, nachdem [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] bereits ein Projekt erstellt hat.  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie den Wert von `DefaultToolsVersion`, bevor Sie ein Projekt erstellen.  
  
## Siehe auch  
 <xref:Microsoft.Build.Utilities.Task.BuildEngine*>   
 <xref:Microsoft.Build.Utilities.Task.BuildEngine2*>   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [Additional Resources](../Topic/Additional%20MSBuild%20Resources.md)