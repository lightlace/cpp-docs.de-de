---
title: "Untersuchen der Mechanismen eines Assistenten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benutzerdefinierte Assistenten, Assistentenprojekte"
ms.assetid: 79917075-a843-40f6-abf8-64d98e5f6bdc
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Untersuchen der Mechanismen eines Assistenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Benutzer können ein Assistentenprojekt sofort verwenden, ohne dass es kompiliert werden muss.  Sobald die erforderlichen Elemente erstellt wurden, werden die beiden folgenden Aktionen durch die VSDIR\-Datei ausgelöst: Im Dialogfeld `New Project` wird das Assistentensymbol angezeigt, und im Dialogfeld `Add New Item` wird der Assistentenname im Kontextmenü angezeigt.  Der Benutzer kann den Assistenten unverzüglich starten, indem er ihn auswählt.  
  
 Wenn der Benutzer den Assistenten startet, wird von der Umgebungsshell parallel das Assistentenmodul erstellt und <xref:EnvDTE.IDTWizard> abgefragt.  Anschließend wird <xref:EnvDTE.IDTWizard.Execute*> aufgerufen, um den Assistenten zu starten.  
  
> [!NOTE]
>  Wenn der Assistent keine Oberfläche besitzt, wird das Projekt mit den vorgegebenen Standardeinstellungen erstellt und im Projektmappen\-Explorer angezeigt. Die Knotenstruktur wird dabei der VSZ\-Datei entnommen.  Im weiteren Verlauf dieses Hilfethemas wird davon ausgegangen, dass der Assistent eine Benutzeroberfläche besitzt.  
  
 Wenn der Assistent über eine Benutzeroberfläche verfügt, werden die Standardwerte der einzelnen Steuerelemente in der HTML\-basierten Assistentenoberfläche vom Benutzer übernommen oder geändert.  Während der Benutzer durch die Seiten des Assistenten navigiert und Änderungen vornimmt, werden im Skriptabschnitt der HTML\-Datei Funktionen wie <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.Navigate*> und <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.Next*> aufgerufen.  
  
 Jedes Mal, wenn der Benutzer im Assistenten andere Optionen auswählt, werden die Benutzereingaben in der Symboltabelle in der Assistentensteuerung erfasst.  Die Symboltabelle passt die Steuerelement\-IDs auf der HTML\-Seite des Assistenten an, um eine 1:1\-Entsprechung zwischen den vom Benutzer ausgewählten Optionen und der Symboltabelle beizubehalten.  
  
 Wenn der Benutzer in der Benutzeroberfläche des Assistenten auf **Fertig stellen** klickt, wird die JScript\-Funktion **OnFinish** aus dem HTML\-Skript aufgerufen.  
  
> [!NOTE]
>  Sie können die **OnFinish**\-Funktion in Default.js anpassen, um beliebige zusätzliche Aufgaben auszuführen.  
  
 Das Assistentenmodul durchsucht dann die Vorlagendateien, analysiert diese und rendert sie entsprechend den vom Benutzer festgelegten Optionen.  Danach werden die gerenderten Dateien in das Projektverzeichnis kopiert und dem Projekt hinzugefügt.  Das neu erstellte Projekt wird in der Visual Studio\-Umgebung geladen, und die projektspezifischen Knoten und Dateien werden im Projektmappen\-Explorer angezeigt.  
  
## Siehe auch  
 <xref:Microsoft.VisualStudio.VsWizard.VCWizCtl>   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Schritte zum Entwerfen eines Assistenten](../ide/steps-to-designing-a-wizard.md)   
 [Anpassen des Assistenten](../ide/customizing-your-wizard.md)