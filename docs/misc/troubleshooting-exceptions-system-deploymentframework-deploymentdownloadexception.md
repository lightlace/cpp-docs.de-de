---
title: "Problembehandlung bei Ausnahmen: System.DeploymentFramework.DeploymentDownloadException"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "DeploymentDownloadException-Klasse"
  - "Anwendungsbereitstellung [C#], DeploymentDownloadException-Klasse"
  - "Bereitstellen von Anwendungen [C#], DeploymentDownloadException-Klasse"
ms.assetid: 55ec7af5-b1d1-4db2-8af8-3c708f521cc7
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "douge"
---
# Problembehandlung bei Ausnahmen: System.DeploymentFramework.DeploymentDownloadException
Eine `T:System.DeploymentFramework.DeploymentDownloadException` tritt auf, wenn beim Herunterladen eines Anwendungsupdates eine Netzwerkausnahme ausgelöst wird.  
  
## Tipps  
 **Untersuchen Sie InnerException, um die zugrunde liegende System.Net\-Ausnahme bzw. System.IO\-Ausnahme zu bestimmen.**  
 Diese Ausnahme tritt immer dann auf, wenn beim Download eines Anwendungsupdates eine Netzwerkausnahme ausgelöst wird. Untersuchen Sie die <xref:System.Exception.InnerException*>\-Eigenschaft der Ausnahme, um die zugrunde liegende Ausnahme zu bestimmen.  
  
## Siehe auch  
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [Try...Catch...Finally Statement](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md)