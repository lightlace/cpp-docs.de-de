---
title: "MSBuild Error MSB3174"
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
  - "MSBuild.GenerateManifest.InvalidValue"
helpviewer_keywords: 
  - "MSB3174"
ms.assetid: 6f9a040c-7f21-40fd-bf74-03f99f265e79
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3174
**MSB3174: Ungültiger Wert für \<Datei\>.**  
  
 Dieser Fehler wird generiert, wenn im Buildprozess beim Überprüfen des Manifestdateiformats ein unspezifisches Problem auftritt.  Die Fehlermeldung bezieht sich auf den Namen der Manifestdatei.  
  
 Diese Fehlermeldung wird generiert, wenn einer der folgenden Parameter falsch festgelegt ist.  Jeder aufgeführte Parameter ist eine <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>\-Eigenschaft oder eine <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest>\-Eigenschaft, wie zum Beispiel <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion*> oder <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest.MinimumRequiredVersion*>.  
  
 Wenn die Aufgabe <xref:Microsoft.Build.Tasks.GenerateApplicationManifest> lautet, gelten die folgenden Voraussetzungen:  
  
|Parameter|Anforderungen|  
|---------------|-------------------|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.AssemblyName*>|Muss ein gültiger Dateiname sein.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.AssemblyVersion*>|Verfügt über die gleichen Voraussetzungen wie <xref:System.Version.#ctor*>.  Alle Oktette müssen größer als 0 \(null\) sein.  Es müssen alle vier Oktette angegeben werden.  Eine leere Zeichenfolge ist zulässig.|  
|<xref:Microsoft.Build.Tasks.GenerateApplicationManifest.ClrVersion*>|Verfügt über die gleichen Voraussetzungen wie <xref:System.Version.#ctor*>.  Alle Oktette müssen größer als 0 \(null\) sein.  Es müssen alle vier Oktette angegeben werden.  Eine leere Zeichenfolge ist zulässig.|  
|<xref:Microsoft.Build.Tasks.GenerateApplicationManifest.OSVersion*>|Verfügt über die gleichen Voraussetzungen wie <xref:System.Version.#ctor*>.  Alle Oktette müssen größer als 0 \(null\) sein.  Es müssen alle vier Oktette angegeben werden.  Eine leere Zeichenfolge ist zulässig.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.Platform*>|Muss **AnyCPU**, **x86**, **x64** oder **Itanium** lauten.  Eine leere Zeichenfolge ist zulässig.|  
|<xref:Microsoft.Build.Tasks.GenerateApplicationManifest.ManifestType*>|Muss **Systemeigen** oder **ClickOnce** sein.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.TargetCulture*>|Eine leere Zeichenfolge ist zulässig.  Kann auch eine neutrale Kultur sein \(wird nur durch den aus zwei Kleinbuchstaben bestehenden Sprachcode angegeben, z. B. "jp" für Japanisch\).  Andernfalls weist dieser Wert über die gleichen Voraussetzungen wie <xref:System.Globalization.CultureInfo.#ctor*> auf.|  
|<xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion*>|Muss das Format v*\#**\#* aufweisen.  Muss höher als v2.0 sein.  Eine leere Zeichenfolge ist zulässig.|  
  
 Wenn die Aufgabe <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest> lautet, gelten die folgenden Voraussetzungen:  
  
|Parameter|Anforderungen|  
|---------------|-------------------|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.AssemblyName*>|Muss ein gültiger Dateiname sein.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.AssemblyVersion*>|Verfügt über die gleichen Voraussetzungen wie <xref:System.Version.#ctor*>.  Alle Oktette müssen größer als 0 \(null\) sein.  Es müssen alle vier Oktette angegeben werden.  Eine leere Zeichenfolge ist zulässig.|  
|<xref:Microsoft.Build.Tasks.GenerateDeploymentManifest.MinimumRequiredVersion*>|Verfügt über die gleichen Voraussetzungen wie <xref:System.Version.#ctor*>.  Alle Oktette müssen größer als 0 \(null\) sein.  Eine leere Zeichenfolge ist zulässig.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.Platform*>|Muss **AnyCPU**, **x86**, **x64** oder **Itanium** lauten.  Eine leere Zeichenfolge ist zulässig.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.TargetCulture*>|Eine leere Zeichenfolge ist zulässig.  Kann auch eine neutrale Kultur sein \(wird nur durch den aus zwei Kleinbuchstaben bestehenden Sprachcode angegeben, z. B. "jp" für Japanisch\).  Andernfalls weist dieser Wert über die gleichen Voraussetzungen wie <xref:System.Globalization.CultureInfo.#ctor*> auf.|  
|<xref:Microsoft.Build.Tasks.GenerateDeploymentManifest.UpdateMode*>|Muss **Vordergrund** oder **Hintergrund** lauten.  Eine leere Zeichenfolge ist zulässig.|  
|<xref:Microsoft.Build.Tasks.GenerateDeploymentManifest.UpdateUnit*>|Muss **Stunden**, **Tage** oder **Wochen** lauten.  Eine leere Zeichenfolge ist zulässig.|  
  
## Siehe auch  
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser*>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion*>   
 [Referenz zum Produkt\- und Paketschema](../Topic/Product%20and%20Package%20Schema%20Reference.md)   
 [Seite "Veröffentlichen", Projekt\-Designer](../Topic/Publish%20Page,%20Project%20Designer.md)   
 [MSBuild Error MSB3116](../misc/msbuild-error-msb3116.md)   
 [MSBuild Error MSB3117](../misc/msbuild-error-msb3117.md)   
 [MSBuild Error MSB3118](../misc/msbuild-error-msb3118.md)   
 [MSBuild Error MSB3185](../misc/msbuild-error-msb3185.md)