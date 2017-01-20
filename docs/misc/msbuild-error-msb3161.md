---
title: "MSBuild Error MSB3161"
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
  - "MSBuild.GenerateBootstrapper.CircularDependency"
helpviewer_keywords: 
  - "MSB3161"
ms.assetid: 2871d071-7c3a-4103-8b14-6ee56564a7f7
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3161
**MSB3161: Bei den folgenden erstellten Paketen wurde eine Ringabhängigkeit entdeckt: \<Paket\>**  
  
 Diese Warnung wird generiert, wenn das Diagramm der Bootstrapperpaketabhängigkeiten eine Ringabhängigkeit aufweist, z. B. A→B→C→A.  Der Bootstrapper kann in einem solchen Fall nicht ermitteln, welches Paket zuerst installiert werden soll.  
  
### So beheben Sie diesen Fehler  
  
-   Heben Sie die Ringabhängigkeit auf, indem Sie entweder die in den Bootstrapperpaketdateien angegebenen Abhängigkeiten ändern oder eines der beteiligten Pakete nicht installieren.  
  
## Siehe auch  
 [Referenz zum Produkt\- und Paketschema](../Topic/Product%20and%20Package%20Schema%20Reference.md)   
 [\<PackageFiles\>\-Element](../Topic/%3CPackageFiles%3E%20Element%20\(Bootstrapper\).md)