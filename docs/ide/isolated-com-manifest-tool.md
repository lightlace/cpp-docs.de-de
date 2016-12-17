---
title: "Isolated COM, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projectname&gt;-Eigenschaftenseiten“"
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
  - "VC.Project.VCManifestTool.RegistrarScriptFile"
  - "VC.Project.VCManifestTool.ComponentFileName"
  - "VC.Project.VCManifestTool.TypeLibraryFile"
  - "VC.Project.VCManifestTool.ReplacementsFile"
dev_langs: 
  - "C++"
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Isolated COM, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projectname&gt;-Eigenschaftenseiten“
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie dieses Dialogfeld, um **Isolated COM**\-Optionen für [Mt.exe](http://msdn.microsoft.com/library/aa375649) anzugeben.  
  
 Um auf dieses Eigenschaftenseiten\-Dialogfeld zuzugreifen, öffnen Sie die Eigenschaftenseiten für das Projekt oder das Eigenschaftenblatt.  Erweitern Sie den Knoten **Manifesttool** unter **Konfigurationseigenschaften**, und wählen Sie dann **Isolated COM** aus.  
  
## Aufgabenliste  
  
-   [Gewusst wie: Erstellen von isolierten Anwendungen zur Verwendung von COM\-Komponenten](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
## UIElement-Liste  
 **Typbibliothekdatei**  
 Legt den Namen der Typbibliothekdatei \(.tlb\), die vom Manifesttool zum Generieren der Manifestdatei verwendet wird, anhand der Option \/tlb fest.  
  
 **Registrierungsskriptdatei**  
 Legt den Namen der Registrierungsskriptdatei \(.rgs\), die vom Manifesttool zum Generieren der Manifestdatei verwendet wird, anhand der Option \/rgs fest.  
  
 **Name der Komponentendatei**  
 Legt den Namen der Ressource, die vom Manifesttool generiert wird, anhand der Option \/dll fest.  Beim Festlegen von Werten für **Typbibliothekdatei** oder **Registrierungsskriptdatei** muss ein Wert für diese Eigenschaft eingegeben werden.  
  
 **Ersetzungsdatei**  
 Legt den vollständigen Pfad zur Datei, die Werte für ersetzbare Zeichenfolgen in der RGS\-Datei enthält, anhand der Option \/replacements fest.  
  
## Siehe auch  
 [Isolierte Anwendungen](http://msdn.microsoft.com/library/aa375190)   
 [Parallele Assemblys](_win32_side_by_side_assemblies)   
 [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md)   
 [Eigenschaftenseiten des Manifesttools](../ide/manifest-tool-property-pages.md)   
 [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../misc/how-to-open-project-property-pages.md)   
 [Gewusst wie: Bearbeiten von Projekteigenschaftenblättern](../misc/how-to-edit-project-property-sheets.md)