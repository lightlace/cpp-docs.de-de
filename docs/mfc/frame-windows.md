---
title: "Rahmenfenster"
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
  - "CFrameWnd-Klasse, Rahmenfenster"
  - "Dokumentrahmenfenster"
  - "Rahmenfenster [C++]"
  - "Rahmenfenster [C++], Information über Rahmenfenster"
  - "MDI [C++], Rahmenfenster"
  - "MFC [C++], Rahmenfenster"
  - "Einzeldokumentoberfläche (SDI)"
  - "Einzeldokumentoberfläche (SDI), Rahmenfenster"
  - "Splitterfenster, und Rahmenfenster"
  - "Ansichten [C++], und Rahmenfenster"
  - "Fensterklassen [C++], Rahmen"
  - "Fenster [C++], MDI"
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Rahmenfenster
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn eine Anwendung unter Windows ausgeführt wird, interagiert der Benutzer auf die Dokumente ein, die in den Rahmenfenstern angezeigt werden.  Ein Dokumentrahmenfenster hat zwei Hauptkomponenten: der Rahmen und der Inhalt, den er Formen.  Ein Dokumentrahmenfenster kann ein Rahmenfenster [\(Single Document Interface](../mfc/sdi-and-mdi.md) \(SDI\) oder ein untergeordnetes Fenster [MDI \(Multiple\-Document](../mfc/sdi-and-mdi.md) \(MDI\) sein.  Windows verwaltet die Interaktion des Benutzers mit dem Rahmenfenster: das Fenster verschieben und dessen Größe ändern, sie und das Minimieren und Maximieren das es geschlossen.  Sie verwalten den Inhalt in den Frame.  
  
## Rahmenfenster und Ansichten  
 Das MFC\-Framework verwendet Rahmenfenster, um Ansichten zu enthalten.  Die beiden Komponenten \- Frame und Inhalt \- werden durch zwei unterschiedliche Klassen in MFC präsentiert und verwaltet.  Eine Rahmenfensterklasse verwaltet die Frames, und einer Ansichtsklasse verwaltet den Inhalt.  Das Ansichtsfenster ist ein untergeordnetes Element des Rahmenfensters.  Zeichnende und anderen Benutzerinteraktion mit dem Dokument finden im Clientbereich der Ansicht, nicht der Clientbereich des Rahmenfensters statt.  Das Rahmenfenster stellt sichtbaren Rahmen um eine Ansicht bereit, die einer Titelleiste und Standardfensterkontrollen wie einem Systemmenü, Schaltflächen, um das Fenster minimiert und maximiert wird vollständig ist und Steuerelementen zum Ändern der Größe des Fensters.  Der "Inhalt" besteht aus den Innenbereich des Fensters, der ausschließlich durch ein untergeordnetes Fenster \- Ansicht gefüllt wird.  Die folgende Abbildung zeigt die Beziehung zwischen einem Rahmenfenster und einer Ansicht an.  
  
 ![Rahmenfensteransicht](../mfc/media/vc37fx1.png "vc37FX1")  
Rahmenfenster und \-ansicht  
  
## Rahmenfenster und Splitterfenster  
 Eine weitere allgemeine Anordnung ist, damit das Rahmenfenster mehrere Ansichten, normalerweise mithilfe [Splitterfenster](../mfc/multiple-document-types-views-and-frame-windows.md) Formen.  In einem unterteilten wird der Clientbereich des Rahmenfensters von einem unterteilten, das wiederum mehrere untergeordnete Fenster ist, aufgerufen Bereiche verfügt, die Ansichten sind.  
  
### Worüber möchten Sie mehr erfahren?  
 **Allgemeine Rahmenfenster\-Themen**  
  
-   [Fensterobjekte](../mfc/window-objects.md)  
  
-   [Rahmenfensterklassen](../mfc/frame-window-classes.md)  
  
-   [Die Rahmenfensterklassen vom Anwendungs\-Assistenten erstellt wurde](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [Rahmenfensterformate](../mfc/frame-window-styles-cpp.md)  
  
-   [Welche Rahmenfenster ausführen](../mfc/what-frame-windows-do.md)  
  
 **Themen zum Verwenden von Rahmenfenstern**  
  
-   [Verwenden der Rahmenfenster](../mfc/using-frame-windows.md)  
  
-   [Erstellen von Dokumentrahmenfenstern](../mfc/creating-document-frame-windows.md)  
  
-   [Zerstören von Rahmenfenstern](../mfc/destroying-frame-windows.md)  
  
-   [Verwalten von untergeordneten MDI\-Fenstern](../mfc/managing-mdi-child-windows.md)  
  
-   [Verwalten der aktuellen Ansicht](../mfc/managing-the-current-view.md) in einem Rahmenfenster, das mehr als Ansicht enthält  
  
-   [Menüs, Steuerleisten und Zugriffstasten \(andere Objekte, die den Platz des Rahmenfensters freigeben\), verwalten](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
 **Themen mit besonderen Rahmenfenster\-Funktionen**  
  
-   Explorer oder Datei\-Manager [Drag & Drop\-Dateien](../mfc/dragging-and-dropping-files-in-a-frame-window.md) der Datei in ein Rahmenfenster  
  
-   [Reagieren auf dynamischen Datenaustausch \(DDE\)](../mfc/responding-to-dynamic-data-exchange-dde.md)  
  
-   [Semimodal\-Zustände: Kontextbezogene Windows\-Hilfe \(andere Fensteraktionen instrumentierend\)](../mfc/orchestrating-other-window-actions.md)  
  
-   [Semimodal\-Zustände: Drucken und Druckvorschau \(andere Fensteraktionen instrumentierend\)](../mfc/orchestrating-other-window-actions.md)  
  
 **Themen auf andere Arten Windows**  
  
-   [Mithilfe von Ansichten](../mfc/using-views.md)  
  
-   [Dialogfelder](../mfc/dialog-boxes.md)  
  
-   [Steuerelemente](../mfc/controls-mfc.md)  
  
## Siehe auch  
 [Windows](../mfc/windows.md)