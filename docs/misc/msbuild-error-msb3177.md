---
title: "MSBuild Error MSB3177"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateManifest.AllowPartiallyTrustedCallers"
helpviewer_keywords: 
  - "MSB3177"
ms.assetid: 0b2417d5-3bc3-4169-b69c-a4a3cbf47882
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3177
**MSB3177: Der \<Verweis\>\-Verweis erlaubt keine Aufrufer, die nicht voll vertrauenswürdig sind.**  
  
 Diese Warnung wird bei der Generierung eines Anwendungsmanifests generiert, wenn es sich bei der Anwendung um eine teilweise vertrauenswürdige Anwendung handelt und *Verweis* als Projektverweis hinzugefügt wurde, über einen starken Namen verfügt und nicht das APTCA\-Attribut aufweist.  
  
### So beheben Sie diesen Fehler  
  
-   Fügen Sie der Assembly, auf die verwiesen wird, das APTCA\-Attribut hinzu. Wenn dies nicht möglich ist, müssen Sie auf die Verwendung verzichten.  
  
## Siehe auch  
 [\<PackageFiles\>\-Element](../Topic/%3CPackageFiles%3E%20Element%20\(Bootstrapper\).md)