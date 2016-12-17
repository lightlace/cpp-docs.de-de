---
title: "MSBuild Error MSB3120"
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
  - "GenerateManifest.FileAssociationExtensionTooLong"
helpviewer_keywords: 
  - "MSB3120"
ms.assetid: 20bc64f5-aadc-4eec-9915-a87a3d7f81ea
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3120
**MSB3120: Dateizuordnungserweiterung '\<Erweiterung \>' überschreitet die maximale zulässige Länge \<maximale Länge\>.**  
  
 Die Anzahl der Zeichen in der Dateizuordnungserweiterung darf die angegebene Zahl nicht überschreiten.  
  
### So beheben Sie diesen Fehler  
  
-   Legen Sie das [ClickOnce Deployment Manifest](../Topic/ClickOnce%20Deployment%20Manifest.md) `extension`\-Attribut auf einen Wert fest, der nicht mehr Zeichen enthält als der zulässige Grenzwert für das Zielbetriebssystem.  
  
## Siehe auch  
 [Seite "Veröffentlichen", Projekt\-Designer](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)