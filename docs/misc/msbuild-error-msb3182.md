---
title: "MSBuild Error MSB3182"
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
  - "MSBuild.GenerateManifest.TargetPathTooLong"
helpviewer_keywords: 
  - "MSB3182"
ms.assetid: b257a206-b12b-453b-97d8-2cb9a0d3dcc9
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3182
**MSB3182: Der Dateiname \<Dateiname\> ist länger als \<Zeichenanzahl\> Zeichen.**  
  
 Diese Warnung wird generiert, wenn der Wert der `TargetPath`\-Eigenschaft zu lang ist.  Er kann sich sowohl auf das Anwendungs\- als auch auf das Bereitstellungsmanifest beziehen.  
  
### So beheben Sie diesen Fehler  
  
-   Kürzen Sie den Wert der `TargetPath`\-Eigenschaft.  
  
## Siehe auch  
 [\<PackageFiles\>\-Element](../Topic/%3CPackageFiles%3E%20Element%20\(Bootstrapper\).md)