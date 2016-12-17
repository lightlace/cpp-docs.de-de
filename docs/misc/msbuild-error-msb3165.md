---
title: "MSBuild Error MSB3165"
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
  - "vsdeploy.chm:13165"
  - "MSBuild.GenerateBootstrapper.DifferingPublicKeys"
helpviewer_keywords: 
  - "MSB3165"
ms.assetid: 2f50462e-947d-4211-b197-e58eddcfd373
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3165
**MSB3165: Der Wert des \<öffentlicher Schlüssel\>\-Attributs in \<Paket\> entspricht nicht dem der Datei "\<Datei\>".**  
  
 Diese Warnung tritt auf, wenn der in der Bootstrapper\-Paketdatei angegebene öffentliche Schlüssel nicht mit der Signatur des verteilbaren Pakets auf dem Datenträger übereinstimmt oder das verteilbare Paket nicht signiert ist.  Der Build nimmt den Wert des öffentlichen Schlüssels des Pakets auf dem Datenträger an, sofern es signiert ist, oder den Hashwert des verteilbaren Pakets auf dem Datenträger, sofern dieses nicht signiert ist.  
  
## Siehe auch  
 [\<PackageFiles\>\-Element](../Topic/%3CPackageFiles%3E%20Element%20\(Bootstrapper\).md)   
 [Referenz zum Produkt\- und Paketschema](../Topic/Product%20and%20Package%20Schema%20Reference.md)