---
title: "Hilfedateien (HTML-Hilfe)"
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
  - "Dateitypen [C++], HTML-Hilfedateien"
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Hilfedateien (HTML-Hilfe)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Dateien werden erstellt, wenn Sie Ihrer Anwendung Hilfeunterstützung vom Typ HTML\-Hilfe hinzufügen. Sie aktivieren dazu das Kontrollkästchen **Kontextbezogene Hilfe** und wählen dann auf der Seite [Erweiterte Features](../mfc/reference/advanced-features-mfc-application-wizard.md) des MFC\-Anwendungs\-Assistenten **HTML\-Hilfeformat** aus.  
  
|Dateiname|Verzeichnis|Anzeige im Projektmappen\-Explorer|Beschreibung|  
|---------------|-----------------|----------------------------------------|------------------|  
|*Projname*.hhp|*Projname*\\hlp|HTML\-Hilfedateien|Hilfeprojektdatei.  Diese Datei enthält die Daten, die für die Kompilierung der Hilfedateien in eine HXS\- oder CHM\-Datei erforderlich sind.|  
|*Projname*.hhk|*Projname*\\hlp|HTML\-Hilfedateien|Enthält einen Index der Hilfethemen.|  
|*Projname*.hhc|*Projname*\\hlp|HTML\-Hilfedateien|Inhalt des Hilfeprojekts.|  
|Makehtmlhelp.bat|*Projname*|Quelldateien|Wird vom System bei der Projektkompilierung zum Erstellen des Hilfeprojekts verwendet.|  
|Afxcore.htm|*Projname*\\hlp|HTML\-Hilfethemen|Enthält Standardhilfethemen für standardmäßige MFC\-Befehle und Bildschirmobjekte.  Fügen Sie dieser Datei eigene Hilfethemen hinzu.|  
|Afxprint.htm|*Projname*\\hlp|HTML\-Hilfethemen|Enthält Hilfethemen für die Druckbefehle.|  
|\*.jpg; \*.gif|*Projname*\\hlp\\Images|Ressourcendateien|Enthalten Bilder für die verschiedenen erstellten Hilfedateithemen.|  
  
## Siehe auch  
 [Für Visual C\+\+\-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)