---
title: "MSBuild-Fehler MSB4135"
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
  - "MSB4135"
ms.assetid: 9192f772-ad13-42f7-b53f-c5e31846fa5f
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "douge"
---
# MSBuild-Fehler MSB4135
**MSB4135: Fehler beim Lesen der Toolsetinformationen aus dem Registrierungsschlüssel "'\<Schlüssel\>'" oder einem Unterschlüssel. '  \<Schlüssel\>'**  
  
 Die benutzerdefinierten, in der Registrierung definierten Toolsetinformationen konnten nicht gelesen werden.  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie in der Registrierung ein benutzerdefiniertes Toolset definiert haben, stellen Sie sicher, dass dieses ein gültiges Registrierungsformat aufweist, den richtigen `ToolsVersion`\-Namen sowie den richtigen `MSBuildBinPath`\-Wert oder `MSBuildToolsPath`\-Wert hat.  
  
## Siehe auch  
 [Standard and Custom Toolset Configurations](../Topic/Standard%20and%20Custom%20Toolset%20Configurations.md)   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [Additional Resources](../Topic/Additional%20MSBuild%20Resources.md)