---
title: "MSBuild Error MSB3116"
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
  - "MSBuild.GenerateManifest.HostInBrowserNotOnlineOnly"
helpviewer_keywords: 
  - "MSB3116"
ms.assetid: bf04c587-d0e2-4d68-bbff-da9a985ea70e
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3116
**MSB3116: Die Anwendung ist für das Hosten im Browser gekennzeichnet, ist aber ebenfalls für die Online\- und Offlineverwendung markiert.  Ändern Sie die Anwendung auf reine Onlineverwendung.**  
  
 Wenn Sie eine WPF\-Webbrowseranwendung bereitstellen, müssen Sie für die <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser*>\-Eigenschaft `True` festlegen.  Wenn für <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser*> `True` festgelegt ist, müssen Sie für die <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.DeployManifest.Install*>\-Eigenschaft `False` festlegen \(um die Installation nur online verfügbar zu machen\).  Wenn letztere Bedingung nicht erfüllt wird, erhalten Sie diese Fehlermeldung.  
  
### So beheben Sie diesen Fehler  
  
-   Legen Sie für die <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.DeployManifest.Install*>\-Eigenschaft `False` fest.  
  
## Siehe auch  
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser*>   
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.DeployManifest.Install*>   
 [Seite "Veröffentlichen", Projekt\-Designer](../Topic/Publish%20Page,%20Project%20Designer.md)