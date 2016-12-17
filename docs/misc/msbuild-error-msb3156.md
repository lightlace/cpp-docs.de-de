---
title: "MSBuild Error MSB3156"
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
  - "MSBuild.GenerateBootstrapper.ProductValidation"
helpviewer_keywords: 
  - "MSB3156"
ms.assetid: 98b1bd42-9efe-44a2-8a43-476edc03590d
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3156
**MSB3156: Die XML\-Validierung konnte für das Element \<Paket\> in \<Ordner\> nicht erfolgreich durchgeführt werden.**  
  
 Diese Warnung wird generiert, wenn das Manifest \(namentlich product.xml\) die XML\-Validierung nicht besteht.  Die spezifischen Probleme werden in einer nachfolgenden Fehlermeldung aufgeführt \([MSBuild Error MSB3159](../misc/msbuild-error-msb3159.md) oder [MSBuild Error MSB3160](../misc/msbuild-error-msb3160.md)\).  
  
### So beheben Sie diesen Fehler  
  
-   Beheben Sie die in den nachfolgenden Fehlermeldungen aufgelisteten Validierungsprobleme des Manifests.  
  
## Siehe auch  
 [Referenz zum Produkt\- und Paketschema](../Topic/Product%20and%20Package%20Schema%20Reference.md)   
 [\<PackageFiles\>\-Element](../Topic/%3CPackageFiles%3E%20Element%20\(Bootstrapper\).md)