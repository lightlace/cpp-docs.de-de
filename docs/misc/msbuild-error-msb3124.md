---
title: "MSBuild Error MSB3124"
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
  - "GenerateManifest.FileAssociationsDuplicateExtensions"
helpviewer_keywords: 
  - "MSB3124"
ms.assetid: d8365103-aa9d-400e-9c24-0a43e2bfbd14
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3124
**MSB3124: Für die Erweiterung '\<Erweiterungsname\>' wurde bereits eine Dateizuordnung erstellt.'**  
  
 Dieser Fehler tritt auf, wenn eine doppelte Dateizuordnungserweiterung gefunden wird.  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie [ClickOnce Deployment Manifest](../Topic/ClickOnce%20Deployment%20Manifest.md)`extension`\-Attribute, die nicht eindeutig sind.  Die Erweiterungsattribute jedes aufgelisteten \<fileAssociation\>\-Elements müssen eindeutig sein.  
  
## Siehe auch  
 [Seite "Veröffentlichen", Projekt\-Designer](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)