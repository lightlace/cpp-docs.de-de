---
title: "Eingabe und Ausgabe, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projectname&gt;-Eigenschaftenseiten“"
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
  - "VC.Project.VCManifestTool.OutputManifestFile"
  - "VC.Project.VCManifestTool.InputResourceManifests"
  - "VC.Project.VCManifestTool.EmbedManifest"
  - "VC.Project.VCManifestTool.AdditionalManifestFiles"
  - "VC.Project.VCManifestTool.DependencyInformationFile"
  - "VC.Project.VCManifestTool.OutputResourceManifest"
  - "VC.Project.VCManifestTool.GenerateCatalogFiles"
dev_langs: 
  - "C++"
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Eingabe und Ausgabe, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projectname&gt;-Eigenschaftenseiten“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie dieses Dialogfeld, um Eingabe\- und Ausgabeoptionen für [Mt.exe](http://msdn.microsoft.com/library/aa375649) anzugeben.  
  
 Um auf dieses Eigenschaftenseiten\-Dialogfeld zuzugreifen, öffnen Sie die Eigenschaftenseiten für das Projekt oder das Eigenschaftenblatt.  Erweitern Sie den Knoten **Manifesttool** unter **Konfigurationseigenschaften**, und wählen Sie dann **Eingabe und Ausgabe**.  
  
## UIElement-Liste  
 **Zusätzliche Manifestdateien**  
 Verwendet die Option **\/manifest**, um die vollständigen Pfade zusätzlicher Manifestdateien anzugeben, die vom Manifesttool verarbeitet oder zusammengeführt werden.  Vollständige Pfade werden durch ein Semikolon getrennt.  
  
 **Eingaberessourcenmanifeste**  
 Verwendet die Option **\/inputresource**, um den vollständigen Pfad einer Ressource vom Typ RT\_MANIFEST anzugeben, die in das Manifesttool eingefügt werden soll.  Auf den Pfad kann die angegebene Ressourcen\-ID folgen.  Beispiele:  
  
 `dll_with_manifest.dll;#1`  
  
 Die Ressourcen\-ID ist optional und lautet in winuser.h standardmäßig CREATEPROCESS\_MANIFEST\_RESOURCE\_ID.  
  
 **Manifest einbetten**  
 **Ja** gibt an, dass die Anwendungsmanifestdatei vom Projektsystem in die Assembly eingebettet wird.  
  
 **Nein** gibt an, dass die Anwendungsmanifestdatei vom Projektsystem als eigenständige Datei erstellt wird.  
  
 **Ausgabemanifestdatei**  
 Gibt den Namen der Ausgabemanifestdatei an.  Diese Eigenschaft ist optional, wenn nur eine Manifestdatei vom Manifesttool verwendet wird.  
  
 **Manifestressourcendatei**  
 Gibt die Ressourcenausgabedateien an, die zur Einbettung des Manifests in die Projektausgabe verwendet werden.  
  
 **Katalogdateien generieren**  
 Verwendet die Option **\/makecdfs**, um anzugeben, dass das Manifesttool Katalogdefinitionsdateien \(CDF\-Dateien\) generiert, die zur Erstellung von Katalogen verwendet werden.  
  
 **Generieren des Manifests von ManagedAssembly**  
 Generieren eines Manifests anhand einer verwalteten Assembly  \(**\-managedassemblyname:***Datei*\).  
  
 **Abhängigkeitselement unterdrücken**  
 Wird mit der Option **\-managedassembly** verwendet.  Dieses Tag unterdrückt die Generierung der Abhängigkeitselemente im endgültigen Manifest.  
  
 **Generieren von Kategorietags**  
 Wird mit der Option **\-managedassembly** verwendet.  Dieses Tag bewirkt, dass die Kategorietags generiert werden.  
  
 **Aktivieren der DPI\-Ausführung**  
 Gibt an, ob die Anwendung die DPI\-Einstellung berücksichtigt.  Standardmäßig ist die Einstellung für MFC\-Projekte **Yes** und andernfalls **No**, da nur MFC\-Projekte DPI\-Einstellungen automatisch berücksichtigen.  Sie können die Einstellung mit **Yes** überschreiben, wenn Sie Code hinzufügen, um unterschiedliche DPI\-Einstellungen zu behandeln.  Die Anwendung wird möglicherweise ungenau oder klein angezeigt, wenn Sie fälschlicherweise angeben, dass sie die DPI berücksichtigt.  
  
## Siehe auch  
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)   
 [Eigenschaftenseiten des Manifesttools](../ide/manifest-tool-property-pages.md)   
 [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../misc/how-to-open-project-property-pages.md)   
 [Gewusst wie: Bearbeiten von Projekteigenschaftenblättern](../misc/how-to-edit-project-property-sheets.md)