---
title: "Erstellen einer MFC-Anwendung im Stil des Datei-Explorers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcexplorer.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Browser, Explorer-ähnliche Anwendungen"
  - "Explorer-ähnliche Anwendungen, Erstellen"
  - "MFC-Anwendungen, Windows Explorer-Format"
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Erstellen einer MFC-Anwendung im Stil des Datei-Explorers
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Viele Windows\-Systemanwendungen verwenden die Benutzeroberfläche \(UI\) für Datei\-Explorer.  Wenn Sie beginnen Datei\-Explorer zum Beispiel sehen Sie eine Anwendung mit einer senkrechten Trennleiste zur Unterteilung des Innenbereichs.  Auf der linken Seite des Innenbereichs befinden sich Navigations\- und Browserelemente, während auf der rechten Seite Einzelheiten zu der im linken Bereich getroffenen Auswahl angezeigt werden.  Wenn der Benutzer auf ein Element im linken Bereich klickt, baut die Anwendung den rechten Bereich neu auf.  In einer MDI\-Anwendung kann der Umfang der im rechten Bereich angezeigten Detailinformationen über die Befehle im Menü **Ansicht** geändert werden. \(In einer SDI\-Anwendung oder einer Anwendung, die mehrere Dokumente der höchsten Ebene unterstützt, können diese Details lediglich über die Symbolleisten\-Schaltflächen geändert werden.\)  
  
 Der Inhalt der Bereiche ist anwendungsspezifisch.  In einem Dateisystembrowser wird im linken Bereich eine hierarchische Ansicht von Verzeichnissen, Computern oder Computergruppen angezeigt, während im rechten Bereich Ordner, einzelne Dateien oder Computer mit den zugehörigen Informationen zu sehen sind.  Die Bereichsfenster müssen jedoch nicht unbedingt Dateien enthalten.  Hier können auch E\-Mail\-Nachrichten, Fehlerberichte oder andere Datenbankelemente angezeigt werden.  
  
 Der Anwendungs\-Assistent erstellt die folgenden Klassen für Sie:  
  
-   Durch die **CLeftView**\-Klasse wird die linke Seite des Innenbereichs definiert.  Sie wird immer von [CTreeView](../../mfc/reference/ctreeview-class.md) abgeleitet.  
  
-   Durch die C*ProjName*View\-Klasse wird die rechte Seite des Innenbereichs definiert.  Sie wird standardmäßig von [CListView](../../mfc/reference/clistview-class.md) abgeleitet, kann jedoch auch einen anderen Ansichtstyp darstellen. Dies hängt von der Klasse ab, die Sie in der Liste **Basisklasse** auf der Seite [Erstellte Klassen](../../mfc/reference/generated-classes-mfc-application-wizard.md) des Assistenten festlegen.  
  
 Die erstellte Anwendung kann über eine SDI \(Single Document Interface\)\- oder eine MDI \(Multiple Document Interface\)\-Architektur bzw. eine Architektur verfügen, die mehrere Dokumente der höchsten Ebene unterstützt.  Jedes von der Anwendung erzeugte Rahmenfenster wird bei Verwendung von [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) vertikal geteilt.  Das Codieren dieses Anwendungstyps ist vergleichbar mit dem Codieren einer gewöhnlichen MFC\-Anwendung, die eine Trennleiste verwendet. Der einzige Unterschied besteht darin, dass dieser Anwendungstyp über separate Steuerelementansichten in jedem Teilfenster verfügt.  
  
 Wenn Sie im rechten Bereich die Standardlistenansicht verwenden, erstellt der Assistent \(nur in MDI\-Anwendungen\) zusätzliche Menüoptionen und Symbolleisten\-Schaltflächen, damit das Ansichtsformat angepasst und z. B. große Symbole, kleine Symbole, die Listenansicht sowie unterschiedliche Detailebenen verwendet werden können.  
  
### So beginnen, eine ausführbare Datei des DateiExplorer\-formats Erstellen MFC  
  
1.  Folgen Sie den Anweisungen unter [Erstellen einer MFC\-Anwendung](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  In der [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) MFC\-Anwendungs\-Assistenten\- Seite wählen Sie das Format **Datei\-Explorer** aus.  
  
3.  Legen Sie ggf. weitere Optionen auf den anderen Seiten des Assistenten fest.  
  
4.  Klicken Sie auf **Fertig stellen**, um die Skelettanwendung zu erzeugen.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Mehrere Dokumenttypen, Ansichten und Rahmenfenster](../../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [Abgeleitete Ansichtsklassen in MFC](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Überlegungen zum Anwendungsentwurf](../../mfc/application-design-choices.md)  
  
## Siehe auch  
 [MFC\-Anwendungs\-Assistent](../../mfc/reference/mfc-application-wizard.md)   
 [Erstellen einer MFC\-Anwendung im Webbrowserstil](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)   
 [Erstellen einer formularbasierten MFC\-Anwendung](../../mfc/reference/creating-a-forms-based-mfc-application.md)