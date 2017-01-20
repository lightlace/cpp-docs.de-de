---
title: "Initialisieren und Bereinigen von Dokumenten und Ansichten"
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
  - "Document-Objekte, Lebenszyklus von"
  - "Dokumente, Bereinigung"
  - "Dokumente, Initialisieren"
  - "Initialisieren von Dokumenten"
  - "Initialisieren von Objekten, Document-Objekte"
  - "Initialisieren von Ansichten"
  - "Ansichten, Bereinigung"
  - "Ansichten, Initialisieren"
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Initialisieren und Bereinigen von Dokumenten und Ansichten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie die folgenden Richtlinien für das Initialisieren und Bereinigen nach Ihren Dokumenten und Ansichten:  
  
-   Das MFC\-Framework initialisiert Dokumente und Ansichten; Sie initialisieren alle Daten, die Sie sie hinzufügen.  
  
-   Das Framework bereinigt als Dokumente und Ansichten schließen; Sie müssen jedem Speicher freigeben, den Sie auf dem Heap fehl Memberfunktionen dieser Dokumente und Ansichten zugeordnet haben.  
  
> [!NOTE]
>  Denken dass die Initialisierung für die ganze Anwendung am besten in der Überschreibung der [InitInstance](../Topic/CWinApp::InitInstance.md)\-Memberfunktion der Klasse `CWinApp` ausgeführt wird, und Bereinigung für die ganze Anwendung ist gut in der Überschreibung der `CWinApp`\-Memberfunktion [ExitInstance](../Topic/CWinApp::ExitInstance.md) durchgeführt.  
  
 Der Lebenszyklus eines Dokuments \(und des Rahmenfensters und Ansicht oder Ansichten\) in eine MDI\-Anwendung ist, wie folgt:  
  
1.  Bei der dynamischen Erstellung wird der Dokumentkonstruktor aufgerufen.  
  
2.  Für jedes neue Dokument wird [OnNewDocument](../Topic/CDocument::OnNewDocument.md) oder der [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) Dokuments aufgerufen.  
  
3.  Der Benutzer interagiert das Dokument während seiner Lebensdauer ein.  Normalerweise geschieht dies, wenn der Benutzer an Dokumentdaten von der Ansicht arbeiten und die Daten auswählen und bearbeitet.  Die Ansicht leitet Änderungen am Dokument für Speicher und Aktualisieren anderer Ansichten weiter.  Während dieser Zeit behandelt das Dokument und Ansicht möglicherweise die Befehle.  
  
4.  Das Framework ruft [DeleteContents](../Topic/CDocument::DeleteContents.md) auf, um Daten für ein bestimmtes Dokument zu löschen.  
  
5.  Der Destruktor des Dokuments wird aufgerufen.  
  
 In einer SDI\-Anwendung wird Schritt 1 einmal ausgeführt, wenn das Dokument zuerst erstellt wird.  Dann werden die Schritte 2 bis 4 wiederholt durchgeführt, wenn ein neues Dokument geöffnet ist.  Das neue Dokument verwendet das vorhandene Dokumentobjekt erneut.  Schließlich wird Schritt 5 ausgeführt, wenn die Anwendung beendet.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Initialisieren von Dokumenten und von Ansichten](../mfc/initializing-documents-and-views.md)  
  
-   [Bereinigen von Dokumenten und von Ansichten](../mfc/cleaning-up-documents-and-views.md)  
  
## Siehe auch  
 [Dokument\-\/Ansichtsarchitektur](../mfc/document-view-architecture.md)