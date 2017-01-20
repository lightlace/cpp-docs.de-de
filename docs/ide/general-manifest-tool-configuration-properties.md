---
title: "Allgemein, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projectname&gt; -Eigenschaftenseiten“"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCManifestTool.MergeRulesFile"
  - "VC.Project.VCManifestTool.UseUnicodeResponseFiles"
  - "VC.Project.VCManifestTool.SuppressStartupBanner"
  - "VC.Project.VCManifestTool.UseFAT32Workaround"
  - "VC.Project.VCManifestTool.VerboseOutput"
  - "VC.Project.VCManifestTool.AssemblyIdentity"
dev_langs: 
  - "C++"
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Allgemein, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projectname&gt; -Eigenschaftenseiten“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie dieses Dialogfeld, um allgemeine Optionen für [Mt.exe](http://msdn.microsoft.com/library/aa375649) anzugeben.  
  
 Um auf dieses Eigenschaftenseiten\-Dialogfeld zuzugreifen, öffnen Sie die Eigenschaftenseiten für das Projekt oder das Eigenschaftenblatt.  Erweitern Sie den Knoten **Manifesttool** unter **Konfigurationseigenschaften**, und wählen Sie dann **Allgemein** aus.  
  
## UIElement-Liste  
 **Startbanner unterdrücken**  
 **Ja \(\/nologo\)** legt fest, dass standardmäßige Copyrightinformationen von Microsoft beim Starten des Manifesttools ausgeblendet werden.  Verwenden Sie diese Option, um unerwünschte Ausgaben in Protokolldateien zu unterdrücken, wenn mt.exe als Teil eines Buildvorgangs oder aus einer Buildumgebung heraus ausgeführt wird.  
  
 **Ausführliche Ausgabe**  
 **Ja \(\/verbose\)** gibt an, dass zusätzliche Buildinformationen während der Generierung des Manifests angezeigt werden.  
  
 **Assemblyidentität**  
 Verwendet die Option \/identity, um eine Identitätszeichenfolge anzugeben, die die Attribute für das [\<assemblyIdentity\> Element](../Topic/%3CassemblyIdentity%3E%20Element%20\(ClickOnce%20Application\).md) umfasst.  Eine Identitätszeichenfolge beginnt mit dem Wert für das `name`\-Attribut, gefolgt von *Attribut* \= *Wert*\-Paaren.  Die Attribute in einer Identitätszeichenfolge werden durch Kommas getrennt.  
  
 Im Folgenden sehen Sie ein Beispiel für eine Identitätszeichenfolge:  
  
 `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`  
  
## Siehe auch  
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)   
 [Eigenschaftenseiten des Manifesttools](../ide/manifest-tool-property-pages.md)   
 [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../misc/how-to-open-project-property-pages.md)   
 [Gewusst wie: Bearbeiten von Projekteigenschaftenblättern](../misc/how-to-edit-project-property-sheets.md)