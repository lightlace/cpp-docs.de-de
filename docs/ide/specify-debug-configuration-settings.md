---
title: "Einstellungen f&#252;r Debugkonfiguration angeben, Assistent &quot;Neues Projekt aus vorhandenen Codedateien erstellen&quot;"
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
  - "vc.appwiz.importwiz.debugsettings"
dev_langs: 
  - "C++"
ms.assetid: 607339a8-9d33-458b-8095-dc73f374e29d
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Einstellungen f&#252;r Debugkonfiguration angeben, Assistent &quot;Neues Projekt aus vorhandenen Codedateien erstellen&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie diese Seite des Assistenten Neues Projekt aus vorhandenen Codedateien erstellen, um Projekteinstellungen für Debugkonfigurationen anzugeben.  
  
## Aufgabenliste  
 [Gewusst wie: Erstellen eines C\+\+\-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## UIElement-Liste  
 **Befehlszeile erstellen**  
 Gibt die Befehlszeile an, durch die das neue Projekt erstellt wird.  Geben Sie z. B. den Namen des Compilers \(mit beliebigen Schaltern oder Argumenten\) oder die Buildskripts an, die zum Erstellen des neuen Projekts verwendet werden sollen.  Diese Option ist aktiviert, wenn auf der Seite **Projekteinstellungen angeben** die Option **Externes Buildsystem verwenden** aktiviert ist. Andernfalls ist sie nicht verfügbar.  
  
 **Befehlszeile erstellen**  
 Gibt die Befehlszeile an, durch die das neue Projekt erneut erstellt wird.  Diese Option ist aktiviert, wenn auf der Seite **Projekteinstellungen angeben** die Option **Externes Buildsystem verwenden** aktiviert ist. Andernfalls ist sie nicht verfügbar.  
  
 **Neue Befehlszeile**  
 Gibt die Befehlszeile an, durch die die von den Buildtools für das neue Projekt generierten Unterstützungsdateien gelöscht werden.  Diese Option ist aktiviert, wenn auf der Seite **Projekteinstellungen angeben** die Option **Externes Buildsystem verwenden** aktiviert ist. Andernfalls ist sie nicht verfügbar.  
  
 **Ausgabe \(für Debuggen\)**  
 Gibt den Verzeichnispfad der Ausgabedateien für die Debugkonfiguration des neuen Projekts an.  Diese Option ist aktiviert, wenn auf der Seite **Projekteinstellungen angeben** die Option **Externes Buildsystem verwenden** aktiviert ist. Andernfalls ist sie nicht verfügbar.  
  
 **Präprozessordefinitionen \(\/D\)**  
 Definiert Präprozessorsymbole für das neue Projekt.  Weitere Informationen finden Sie unter [\/D \(Präprozessordefinitionen\)](../build/reference/d-preprocessor-definitions.md).  
  
 **Suchpfad einschließen \(\/I\)**  
 Legt Verzeichnispfade fest, die der Verzeichnisliste hinzugefügt werden sollen. Diese werden vom Compiler zum Auflösen der an Präprozessordirektiven im neuen Projekt übergebenen Dateiverweise durchsucht.  Weitere Informationen finden Sie unter [\/I \(Zusätzliche Includeverzeichnisse\)](../build/reference/i-additional-include-directories.md).  
  
 **Erzwungene hinzugefügte Dateien \(\/FI\)**  
 Gibt Headerdateien an, die beim Erstellen des neuen Projekts verarbeitet werden sollen.  Weitere Informationen finden Sie unter [\/FI \(Name der expliziten Includedatei\)](../build/reference/fi-name-forced-include-file.md).  
  
 **.NET\-Assemblysuchpfade \(\/AI\)**  
 Gibt die Verzeichnispfade an, die vom Compiler zum Auflösen der an Präprozessordirektiven im neuen Projekt übergebenen .NET\-Assemblyverweise durchsucht werden sollen.  Weitere Informationen finden Sie unter [\/AI \(Metadatenverzeichnisse festlegen\)](../build/reference/ai-specify-metadata-directories.md).  
  
 **Erzwungenes Verwenden von .NET\-Assemblys \(\/FU\)**  
 Gibt die beim Erstellen des neuen Projekts zu verarbeitenden .NET\-Assemblys an.  Weitere Informationen finden Sie unter [\/FU \(Name der expliziten \#using\-Datei\)](../build/reference/fu-name-forced-hash-using-file.md).  
  
## Siehe auch  
 [Projekteinstellungen angeben, Assistent "Neues Projekt aus vorhandenen Codedateien erstellen"](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)