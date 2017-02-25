---
title: "Untersuchen des grundlegenden Assistentenprojekts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benutzerdefinierte Assistenten, Dateien erstellt"
  - "Benutzerdefinierte Assistenten, Assistentenprojekte"
ms.assetid: c6423e3c-ddb0-43e0-b8e5-9e3a98a7908c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Untersuchen des grundlegenden Assistentenprojekts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie das grundlegende Projekt mithilfe des [benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md) erstellt haben, untersuchen Sie die neu erstellten Dateien.  
  
1.  Erweitern Sie das Projekt im **Projektmappen\-Explorer**, und untersuchen Sie [die Dateien](../ide/files-created-for-your-wizard.md), die der Assistent für das Projekt erstellt hat.  
  
2.  Doppelklicken Sie auf **Default.js**, um die [JScript\-Datei](../ide/jscript-file.md) des Projekts im Code\-Editor zu öffnen.  Diese Datei enthält JScript\-Funktionen, durch die das Projekt erstellt wird, wenn der Benutzer im Assistenten auf **Fertig stellen** klickt.  Überprüfen Sie die Funktionen und TODO\-Anmerkungen in dieser Datei.  
  
3.  Wenn das Projekt eine Benutzeroberfläche besitzt, suchen Sie nach dem Ordner [HTML\-Dateien](../ide/html-files.md). Wie Sie feststellen können, enthält dieser die Anzahl von HTM\-Dateien, die Sie auf der Seite [Anwendungseinstellungen](../ide/application-settings-custom-wizard.md) im benutzerdefinierten Assistenten angegeben haben.  Doppelklicken Sie auf **Default.htm**, um die HTML\-Hauptseite des Projekts im [HTML\-Designer](../Topic/HTML%20Designer.md) zu öffnen.  Sie können die HTML\-Seite entweder in der [Design View](../Topic/Design%20View1.md) oder in der HTML\-Ansicht als [HTML\-Code](assetId:///7bb90672-b36a-4cf9-9bbc-677c9b956318) anzeigen.  Wechseln Sie zur HTML\-Codeansicht, und überprüfen Sie den HTML\-Code.  Klicken Sie auf die Schaltfläche **Nur Skript\-Ansicht** \(in der oberen rechten Ecke des Bearbeitungsfensters der HTML\-Ansicht, neben der Dropdownliste **Ereignisse**\), und untersuchen Sie den JScript\-Code in der HTM\-Datei.  Diese Datei enthält standardmäßig die JScript\-Funktionen, durch die der Assistent initialisiert und geladen wird, und stellt das Standardverhalten für die **IVCWizCtrlUI**\-Schnittstelle bereit.  Weitere Informationen finden Sie in den Erläuterungen zum <xref:Microsoft.VisualStudio.VsWizard.VCWizCtl>\-Objekt der Co\-Klasse.  
  
4.  Speichern und schließen Sie das Assistentenprojekt.  
  
5.  Öffnen Sie das Dialogfeld **Neues Projekt** in Visual Studio, und suchen Sie das Symbol für den Assistenten.  Doppelklicken Sie auf das Symbol, um den Assistenten anzuzeigen.  Untersuchen Sie die grundlegenden Assistentenseiten, die vom benutzerdefinierten Assistenten erstellt wurden.  Beachten Sie, dass die erste Seite einige HTML\-Beispielsteuerelemente und die Standardschaltflächen **Fertig stellen**, **Abbrechen** und **Hilfe** enthält.  
  
6.  Klicken Sie auf **Fertig stellen**, um mit dem Assistenten ein neues Projekt zu erstellen.  Standardmäßig erstellt der Assistent zwei Textdateien: "ReadMe.txt" und "Sample.txt".  In diesen Dateien wird das Projekt, das der Assistent erstellt hat, beschrieben.  Schließen Sie das Projekt, und öffnen Sie das Assistentenprojekt erneut.  
  
7.  Lesen Sie das Thema [Untersuchen der Mechanismen eines Assistenten](../ide/examining-the-mechanics-of-a-wizard.md), um ein besseres Verständnis dafür zu erhalten, auf welche Weise das Projekt von der Visual Studio\-Umgebung und dem Visual C\+\+\-Assistentenmodul erstellt wurde, nachdem Sie den Assistenten ausgeführt haben.  
  
 Nun können Sie mit der [Anpassung des benutzerdefinierten Assistenten](../ide/customizing-your-wizard.md) beginnen.  
  
## Siehe auch  
 [Benutzerdefinierter Assistent](../ide/custom-wizard.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Schritte zum Entwerfen eines Assistenten](../ide/steps-to-designing-a-wizard.md)   
 [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md)   
 [Bereitstellen kontextbezogener Hilfe](../ide/providing-context-sensitive-help.md)   
 [Anpassen des Assistenten](../ide/customizing-your-wizard.md)