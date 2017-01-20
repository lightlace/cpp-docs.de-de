---
title: "MSBuild Error MSB3118"
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
  - "MSBuild.GenerateManifest.UseApplicationTrustInvalidFrameworkVersion"
helpviewer_keywords: 
  - "MSB3118"
ms.assetid: 9bf5b430-0cfb-4da5-a7f7-04d69f20cce1
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3118
**MSB3118: Die Anwendung ist auf die Verwendung der Anwendungsvertrauensstellung festgelegt, aber die TargetFrameworkVersion ist nicht v3.5 oder höher.**  
  
 Dieser Fehler tritt auf, wenn Sie für die <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.UseApplicationTrust*>\-Eigenschaft `True` festlegen und für die <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion*>\-Eigenschaft eine niedrigere Version als `v3.5` festlegen \(z. B. `v2.0`\).  
  
### So beheben Sie diesen Fehler  
  
-   Legen Sie für die <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion*>\-Eigenschaft den Wert `v3.5` oder höher fest.  
  
## Siehe auch  
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.UseApplicationTrust*>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.UseApplicationTrust*>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion*>   
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser*>   
 [Seite "Veröffentlichen", Projekt\-Designer](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [MSBuild Error MSB3116](../misc/msbuild-error-msb3116.md)   
 [MSBuild Error MSB3117](../misc/msbuild-error-msb3117.md)   
 [MSBuild Error MSB3119](../misc/msbuild-error-msb3119.md)   
 [MSBuild Error MSB3174](../misc/msbuild-error-msb3174.md)   
 [MSBuild Error MSB3185](../misc/msbuild-error-msb3185.md)