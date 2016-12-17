---
title: "Eigenschaftenseite &quot;NMake&quot;"
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
  - "VC.Project.VCNMakeTool.ReBuildCommandLine"
  - "VC.Project.VCNMakeTool.CleanCommandLine"
  - "VC.Project.VCNMakeTool.Output"
  - "VC.Project.VCNMakeTool.BuildCommandLine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NMake (Eigenschaftenseite)"
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Eigenschaftenseite &quot;NMake&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Über die Eigenschaftenseite **NMake** können Sie Buildeinstellungen für NMake\-Projekte angeben.  
  
 Weitere Informationen über NMake\-Projekte finden Sie unter [Erstellen eines Makefile\-Projekts](../ide/creating-a-makefile-project.md).  
  
 Die Eigenschaftenseite **NMake** enthält die folgenden Eigenschaften:  
  
## UIElement-Liste  
 **Befehlszeile erstellen**  
 Legt den Befehl fest, der ausgeführt werden soll, nachdem im Menü **Erstellen** der Befehl **Erstellen** ausgewählt wurde.  
  
 **"Alles neu erstellen"\-Befehlszeile**  
 Legt den Befehl fest, der ausgeführt werden soll, nachdem im Menü **Erstellen** der Befehl **Alles neu erstellen** ausgewählt wurde.  
  
 **Neue Befehlszeile**  
 Legt den Befehl fest, der ausgeführt werden soll, nachdem im Menü **Erstellen** der Befehl **Bereinigen** ausgewählt wurde.  
  
 **Output**  
 Legt den Namen der Datei fest, die die Ausgabe für die Befehlszeile enthält.  Dieser Dateiname basiert standardmäßig auf dem Projektnamen.  
  
 **Präprozessordefinitionen**  
 Gibt allein den Quelldateien verwendeten Präprozessordefinitionen an.  Der Standardwert wird von der aktuellen Plattform und Konfiguration bestimmt.  
  
 **Suchpfad einschließen**  
 Gibt die Verzeichnisse an, in denen der Compiler nach Includedateien sucht.  
  
 **Erzwungene Includes**  
 Gibt Dateien an, die der Präprozessor automatisch verarbeitet, auch wenn sie nicht in den Projektdateien enthalten sind.  
  
 **Assemblysuchpfade**  
 Gibt die Verzeichnisse an, in denen .NET Framework sucht, wenn es versucht, .NET\-Assemblys aufzulösen.  
  
 **Erzwungenes Verwenden von Assemblys**  
 Gibt Assemblys an, die .NET Framework automatisch verarbeitet.  
  
 **Zusätzliche Optionen**  
 Gibt alle zusätzlichen Compilerschalter für IntelliSense zur Verwendung beim Anaysieren von C\+\+\-Dateien an.  
  
 Informationen zum Zugriff auf die **NMake**\-Eigenschaftenseite finden Sie unter [Gewusst wie: Festlegen von Projekteigenschaften mit Eigenschaftenseiten](../misc/how-to-specify-project-properties-with-property-pages.md).  
  
 Informationen zum programmgesteuerten Zugriff auf Member dieses Objekts finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>.  
  
## Siehe auch  
 [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)   
 [Gewusst wie: Aktivieren von IntelliSense für Makefile\-Projekte](../ide/how-to-enable-intellisense-for-makefile-projects.md)