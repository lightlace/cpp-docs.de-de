---
title: "MSBuild Error MSB3179"
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
  - "MSBuild.GenerateManifest.ComImport"
helpviewer_keywords: 
  - "MSB3179"
ms.assetid: fa744f6c-e398-4e60-b4f7-455ace7e3bd2
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3179
**MSB3179: Problem beim Isolieren der COM\-Referenz \<Assembly\>: \<Fehler\>**  
  
 Diese generische Fehlermeldung gibt ein Problem mit der Generierung registrierungsfreier COM\-Einträge im Anwendungsmanifest an \(wie durch den `IsolatedComReferences`\-Aufgabenparameter angegeben\).  Der letzte Teil der Fehlermeldung enthält spezifischere Informationen über die Art des Problems.  Möglicherweise besteht die Fehlerursache darin, dass die registrierungsfreien COM\-Einträge nicht ordnungsgemäß auf dem Buildcomputer registriert sind.  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass alle COM\-Komponenten auf dem Buildcomputer registriert sind.  
  
## Siehe auch  
 [\<PackageFiles\>\-Element](../Topic/%3CPackageFiles%3E%20Element%20\(Bootstrapper\).md)