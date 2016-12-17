---
title: "MSBuild Error MSB3141"
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
  - "MSBuild.GenerateBootstrapper.MissingVerificationInformation"
  - "vsdeploy.chm:13141"
helpviewer_keywords: 
  - "MSB3141"
ms.assetid: f32ce5fd-bb82-4a8b-aebe-61efef89cdc1
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3141
**MSB3141: Es wurde kein PublicKey\- oder Hash\-Attribut für Datei \<Datei\> in Element \<Paket\> angegeben.**  
  
 Dieser Fehler wird ausgegeben, wenn Sie versuchen, HomeSite für die Bootstrapperpakete zu verwenden.  Das Bootstrappermanifest enthält zur Laufzeit jedoch keine korrekten Informationen für die Dateiüberprüfung \(einen öffentlichen Schlüssel oder einen Hash\).  
  
### So beheben Sie diesen Fehler  
  
-   Laden Sie die Paketdatei herunter, für die die Informationen fehlen, und kopieren Sie sie in den Bootstrappercache.  
  
## Siehe auch  
 [\<PackageFiles\>\-Element](../Topic/%3CPackageFiles%3E%20Element%20\(Bootstrapper\).md)