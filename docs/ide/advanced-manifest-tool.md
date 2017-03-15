---
title: "Erweitert, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projectname&gt; -Eigenschaftenseiten“"
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
  - "VC.Project.VCManifestTool.KeyFile"
  - "VC.Project.VCManifestTool.UpdateFileHashes"
  - "VC.Project.VCManifestTool.UpdateFileHashesSearchPath"
  - "VC.Project.VCManifestTool.ValidateSignature"
  - "VC.Project.VCManifestTool.KeyContainer"
dev_langs: 
  - "C++"
ms.assetid: 3d587366-05ea-4956-a978-313069660735
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Erweitert, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projectname&gt; -Eigenschaftenseiten“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie dieses Dialogfeld, um erweiterte Optionen für [Mt.exe](http://msdn.microsoft.com/library/aa375649) anzugeben.  
  
 Um auf dieses Eigenschaftenseiten\-Dialogfeld zuzugreifen, öffnen Sie die Eigenschaftenseiten für das Projekt oder das Eigenschaftenblatt.  Erweitern Sie den Knoten **Manifesttool** unter **Konfigurationseigenschaften**, und wählen Sie dann **Erweitert** aus.  
  
## UIElement-Liste  
 **Dateihashes aktualisieren**  
 Legt anhand der Option \/hashupdate fest, dass das Manifesttool den in `<file>`\-Elementen festgelegten Hash von Dateien berechnet und die Hash\-Attribute anschließend anhand des berechneten Werts aktualisiert.  
  
 **Suchpfad für Dateihashes aktualisieren**  
 Gibt den Suchpfad für Dateien an, auf die in `<file>`\-Elementen verwiesen wird.  Diese Option verwendet auch die Option \/hashupdate.  
  
## Siehe auch  
 [\<file\> Element](../Topic/%3Cfile%3E%20Element%20\(ClickOnce%20Application\).md)   
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)   
 [Eigenschaftenseiten des Manifesttools](../ide/manifest-tool-property-pages.md)   
 [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../misc/how-to-open-project-property-pages.md)   
 [Gewusst wie: Bearbeiten von Projekteigenschaftenblättern](../misc/how-to-edit-project-property-sheets.md)