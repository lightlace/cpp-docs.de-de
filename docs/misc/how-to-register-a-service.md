---
title: "Gewusst wie: Registrieren von Diensten"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Dienste, Registrieren"
ms.assetid: d086be78-ec3c-43cc-b799-5180a71e19f1
caps.latest.revision: 16
caps.handback.revision: "16"
manager: "douge"
---
# Gewusst wie: Registrieren von Diensten
Managed Package Framework \(MPF\) stellt Attribute bereit, um die Registrierung der verwalteten Dienste zu steuern. Das RegPkg\-Dienstprogramm verwendet diese Attribute zum Registrieren eines Diensts mit [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
## Beispiel  
 Der folgende Code stammt aus [VSSDK\-Beispiele](../misc/vssdk-samples.md).  
  
 [!CODE [VSSDKRegisterService#1](../CodeSnippet/VS_Snippets_VSSDK/vssdkregisterservice#1)]  
  
 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> registriert den Dienst SMyGlobalService mit [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]. Weitere Informationen zu <xref:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute> und <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> finden Sie unter [Registrieren und Aufheben der Registrierung von VSPackages](../Topic/Registering%20and%20Unregistering%20VSPackages.md).  
  
 Verwenden Sie <xref:Microsoft.VisualStudio.Shell.ProvideServiceOverrideAttribute> statt <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute>, um einen Dienst zu registrieren, der einen anderen Dienst gleichen Namens ersetzt.  
  
## Robuste Programmierung  
 Um das erneute Kompilieren eines Dienstanbieters ohne Änderung des Dienstclients \(oder umgekehrt\) zu vereinfachen, können Sie den Dienst und die zugehörigen Schnittstellen in einem separaten Assembly\-Modul definieren. Der folgende Code stammt aus der Datei "IMyGlobalService.cs" im Reference.Services \(C\#\)\-Beispiel.  
  
 [!CODE [VSSDKRegisterService#2](../CodeSnippet/VS_Snippets_VSSDK/vssdkregisterservice#2)]  
  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute> ist erforderlich, um die Schnittstelle aus nicht verwaltetem Code abzurufen.  
  
> [!NOTE]
>  Sie können zwar den gleichen Typ oder die GUID für den Dienst und die Schnittstelle verwenden, es ist jedoch empfehlenswert, die beiden zu trennen, da der Dienst unterschiedliche Schnittstellen verfügbar machen kann.  
  
## Siehe auch  
 [Registering VSPackages](assetId:///31e6050f-1457-4849-944a-a3c36b76f3dd)   
 [Service – Grundlagen](../Topic/Service%20Essentials.md)