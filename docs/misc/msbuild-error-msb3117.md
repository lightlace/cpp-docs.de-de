---
title: "MSBuild Error MSB3117"
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
  - "MSBuild.GenerateManifest.HostInBrowserInvalidFrameworkVersion"
helpviewer_keywords: 
  - "MSB3117"
ms.assetid: 18aec642-6000-4626-bf75-f3547769c780
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3117
**MSB3117: Die Anwendung ist auf das Hosten im Browser festgelegt, für die TargetFrameworkVersion wurde jedoch v2.0 angegeben.**  
  
 Eine WPF\-Webbrowseranwendung wurde bereitgestellt, wobei für die <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser*>\-Eigenschaft `True` festgelegt ist, TargetFrameworkVersion jedoch auf `v2.0` oder `v3.0` eingestellt wurde.  Wenn Sie diese Einstellung verwenden, müssen Sie für die <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion*>\-Eigenschaft außerdem mindestens den Wert `v3.5` festlegen.  
  
### So beheben Sie diesen Fehler  
  
-   Legen Sie den Wert der <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion*>\-Eigenschaft auf mindestens `v3.5` fest.  
  
## Siehe auch  
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser*>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion*>   
 [Seite "Veröffentlichen", Projekt\-Designer](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [MSBuild Error MSB3116](../misc/msbuild-error-msb3116.md)   
 [MSBuild Error MSB3118](../misc/msbuild-error-msb3118.md)   
 [MSBuild Error MSB3174](../misc/msbuild-error-msb3174.md)   
 [MSBuild Error MSB3185](../misc/msbuild-error-msb3185.md)