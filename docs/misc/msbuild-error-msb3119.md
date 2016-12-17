---
title: "MSBuild Error MSB3119"
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
  - "GenerateManifest.FileAssociationExtensionMissingLeadDot"
helpviewer_keywords: 
  - "MSB3119"
ms.assetid: 52d68b0e-01d4-436f-a96c-733fd20a8c04
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3119
**MSB3119: Dateizuordnungserweiterungen müssen mit einem Punktzeichen \(.\) beginnen.**  
  
 Dieser Fehler tritt auf, wenn Sie eine Dateizuordnung konfigurieren und die Erweiterung nicht mit einem Punktzeichen \(.\) beginnt.  
  
### So beheben Sie diesen Fehler  
  
-   Legen Sie das [ClickOnce Deployment Manifest](../Topic/ClickOnce%20Deployment%20Manifest.md) `extension`\-Attribut auf einen Wert fest, der mit einem Punktzeichen \(.\) beginnt, z. B. ".doc".  
  
## Siehe auch  
 [Seite "Veröffentlichen", Projekt\-Designer](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)