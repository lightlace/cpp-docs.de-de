---
title: "Hilfedateien (WinHelp)"
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
  - "Dateitypen [C++], WinHelp-Dateien"
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Hilfedateien (WinHelp)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Dateien werden erstellt, wenn Sie der Anwendung WinHelp\-Hilfeunterstützung hinzufügen. Sie aktivieren dazu das Kontrollkästchen **Kontextbezogene Hilfe** und wählen dann auf der Seite [Erweiterte Features](../mfc/reference/advanced-features-mfc-application-wizard.md) des MFC\-Anwendungs\-Assistenten **WinHelp\-Format** aus.  
  
|Dateiname|Verzeichnis|Anzeige im Projektmappen\-Explorer|Beschreibung|  
|---------------|-----------------|----------------------------------------|------------------|  
|*Projname*.hpj|*Projname*\\hlp|Quelldateien|Hilfeprojektdatei, mit der der Hilfecompiler die Hilfedatei des Programms oder Steuerelements erstellt.|  
|*Projname*.rtf|*Projname*\\hlp|Hilfedateien|Enthält Themenvorlagen, die Sie bearbeiten können, sowie Informationen zur Anpassung der HPJ\-Datei.|  
|*Projname*.cnt|*Projname*\\hlp|Hilfedateien|Stellt die Struktur für das Fenster **Inhalt** in der Windows\-Hilfe bereit.|  
|Makehelp.bat|*Projname*|Quelldateien|Wird vom System bei der Projektkompilierung zum Erstellen des Hilfeprojekts verwendet.|  
|Print.rtf|*Projname*\\hlp|Hilfedateien|Wird erstellt, wenn das Projekt Druckunterstützung \(Standard\) umfasst.  Diese Datei beschreibt die Druckbefehle und Dialogfelder.|  
|\*.bmp|*Projname*\\hlp|Ressourcendateien|Enthalten Bilder für die verschiedenen erstellten Hilfedateithemen.|  
  
 Sie können einem MFC\-ActiveX\-Steuerelementprojekt WinHelp\-Unterstützung hinzufügen, indem Sie auf der Registerkarte [Anwendungseinstellungen](../mfc/reference/application-settings-mfc-activex-control-wizard.md) des MFC\-ActiveX\-Steuerelement\-Assistenten **Hilfedateien erstellen** auswählen.  Die folgenden Dateien werden dem Projekt hinzugefügt, nachdem Sie einem MFC\-ActiveX\-Steuerelement Hilfeunterstützung hinzugefügt haben:  
  
|Dateiname|Verzeichnis|Anzeige im Projektmappen\-Explorer|Beschreibung|  
|---------------|-----------------|----------------------------------------|------------------|  
|*Projname*.hpj|*Projname*\\hlp|Quelldateien|Projektdatei, mit der der Hilfecompiler die Hilfedatei des Programms oder Steuerelements erstellt.|  
|*Projname*.rtf|*Projname*\\hlp|Project|Enthält Themenvorlagen, die Sie bearbeiten können, sowie Informationen zur Anpassung der HPJ\-Datei.|  
|Makehelp.bat|*Projname*|Quelldateien|Wird vom System bei der Projektkompilierung zum Erstellen des Hilfeprojekts verwendet.|  
|Bullet.bmp|*Projname*|Ressourcendateien|Wird in Standard\-Hilfedateithemen zur Darstellung von Listen mit Aufzählungszeichen verwendet.|  
  
## Siehe auch  
 [Für Visual C\+\+\-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)