---
title: "Dokumente, Ansichten und das Framework"
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
  - "Anwendungsobjekte [C++], Beziehung zu anderen MFC-Objekten"
  - "Anwendungen [MFC]"
  - "Document-Objekte, In Beziehung zu anderen MFC-Objekten"
  - "Dokumentvorlagen, Vorlagenobjekte"
  - "Dokument-/Ansichtsarchitektur, Informationen über Dokument-/Ansichtsarchitektur"
  - "Dokumente [C++]"
  - "MFC [C++], Anwendungsframework"
  - "MFC [C++], Dokumente"
  - "MFC [C++], Ansichten"
  - "MFC-Objektbeziehungen"
  - "Objekte [C++], MFC-Anwendungen"
  - "Thread-Objekte"
  - "View-Objekte, Beziehung zu anderen MFC-Objekten"
ms.assetid: 409ddd9b-66ad-4625-84f7-bf55a41d697b
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Dokumente, Ansichten und das Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im eine des MFC\-Frameworks gelten die Konzepte des Dokuments und der Ansicht.  Ein Dokument ist ein Datenobjekt, auf das der Benutzer in einer Bearbeitung interagiert.  Sie wird durch den `New` oder **Öffnen** auf den Befehl **Datei** Menü erstellt und wird in der Regel in einer Datei gespeichert. \(Standard\-MFC\-Dokumente, die von Klasse **CDocument** abgeleitet sind, sind für aktiven Dokumenten und OLE\-Verbunddokumenten.\) Eine Ansicht ist ein Window\-Objekt, durch das der Benutzer auf ein Dokument interagiert.  
  
 Die Schlüsselobjekte in einer ausgeführten Anwendung sind:  
  
-   Das Dokument oder die Dokumente.  
  
     die Dokumentklasse \(wird von [CDocument](../mfc/reference/cdocument-class.md) abgeleitet\) gibt den Daten der Anwendung.  
  
     Wenn Sie OLE\-Funktionalität in Ihrer Anwendung wünschen, leiten Sie die Dokumentklasse von [COleDocument](../mfc/reference/coledocument-class.md) oder einer der abgeleiteten Klassen, je nach Typ der Funktionalität, die Sie benötigen.  
  
-   Die Ansicht oder die Ansichten.  
  
     die Ansichtsklasse \(wird von [CView](../mfc/reference/cview-class.md) abgeleitet\) ist das Fenster des Benutzers "auf den Daten." Die Ansichtsklassenkontrollen, wie der Benutzer die Daten des Dokuments wird und interagiert.  In einigen Fällen müssen Sie ein Dokument mehrere Ansichten der Daten verfügen.  
  
     Wenn Sie einen Bildlauf erfordern, leiten Sie von [CScrollView](../mfc/reference/cscrollview-class.md).  Wenn die Ansicht eine Benutzeroberfläche verfügt, die in einer Dialogfeldvorlagenressource angeordnet wird, leiten Sie von [CFormView](../mfc/reference/cformview-class.md).  Für einfache Textdaten verwenden Sie oder leiten Sie von [CEditView](../mfc/reference/ceditview-class.md).  Bei einer formularbasierten Datenzugriffs\-Anwendung wie ein Dateneingabeprogramm, leiten Sie von [CRecordView](../mfc/reference/crecordview-class.md) \(für ODBC\).  Zudem sind Klassen [CTreeView](../mfc/reference/ctreeview-class.md), [CListView](../mfc/reference/clistview-class.md) und [CRichEditView](../mfc/reference/cricheditview-class.md) verfügbar.  
  
-   Die Rahmenfenster  
  
     Ansichten sind angezeigtes innerhalb Dokumentrahmenfenster "." In einer SDI\-Anwendung ist das Dokumentrahmenfenster auch "das Hauptrahmenfenster" für die Anwendung.  In einer MDI\-Anwendung sind Dokumentfenster die untergeordneten Fenster, die innerhalb eines Hauptrahmenfensters angezeigt werden.  Die abgeleitete Hauptrahmenfensterklasse gibt Stilen und anderen Eigenschaften der Rahmenfenster an, die die Ansichten enthalten.  Wenn Sie Rahmenfenster anpassen müssen, leiten Sie von [CFrameWnd](../mfc/reference/cframewnd-class.md), um das für SDI\-Anwendungen Dokumentrahmenfenster anzupassen.  Sind von [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), um das Hauptrahmenfenster für MDI\-Anwendungen anzupassen.  Leiten Sie außerdem eine Klasse von [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md), um unterschiedliche Weise MDI\-Dokumentrahmenfenster anzupassen, die die Anwendung unterstützt.  
  
-   Die Normal\-Vorlage oder Vorlagen  
  
     Eine Normal\-Vorlage instrumentiert die Dokumentenerstellung, Ansichten und Rahmenfenster.  Eine bestimmte Dokumentvorlagenklasse, die von der [CDocTemplate](../mfc/reference/cdoctemplate-class.md)\- Klasse abgeleitet ist, erstellt und verwaltet alle geöffneten Dokumenten aus einem Typ.  Anwendungen, die mehr unterstützen, wenn ein Typ Dokument enthalten mehrere Dokumentvorlagen.  Verwenden Sie [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md)\-Klasse für SDI\-Anwendungen, oder verwenden Sie [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)\-Klasse für MDI\-Anwendungen.  
  
-   Das Anwendungsobjekt  
  
     die Anwendungsklasse \(wird von [CWinApp](../mfc/reference/cwinapp-class.md) abgeleitet\) steuert alle Objekte oben und Anwendungsverhalten gibt z Initialisierung und Bereinigung an.  Der die und nur das Anwendungsobjekt Anwendung erstellt und verwaltet die Dokumentvorlagen für die Dokumenttypen, welche die Anwendung unterstützt.  
  
-   Threadobjekte  
  
     Wenn die Anwendung separate Threads der Ausführung erstellt \- beispielsweise, Berechnungen im Hintergrund ausführen \- Sie verwenden die Klassen, die von [CWinThread](../mfc/reference/cwinthread-class.md) abgeleitet werden.  [CWinApp](../mfc/reference/cwinapp-class.md) wird auch von `CWinThread` abgeleitet und dem ersten Ausführungsthread \(oder des Hauptprozesses\) in der Anwendung darstellt.  Sie können MFC in den sekundären Threads ebenfalls verwenden.  
  
 In einer laufenden Anwendung reagiert diese Objekte kooperativ auf Benutzeraktionen, Grenze zusammen durch Befehle und andere Meldungen.  Ein Einzelanwendungsobjekt verwaltet einen oder mehrere. Dokumentvorlagen  Jede Normal\-Vorlage erstellt und verwaltet einen oder mehrere Dokumente \(abhängig, ob die SDI\-Anwendung oder MDI ist\).  Die Benutzer und bearbeitet ein Dokument durch eine Ansicht, die innerhalb eines Rahmenfensters enthalten ist.  Die folgende Abbildung zeigt die Beziehungen zwischen diesen Objekten für eine SDI\-Anwendung an.  
  
 ![Objekte in einer ausgeführten SDI&#45;Anwendung](../mfc/media/vc386v1.png "vc386V1")  
Objekte in einer ausgeführten SDI\-Anwendung  
  
 Der Rest dieser Familie der Artikel erklärt, wie die Frameworktools, der MFC\-Anwendungs\-Assistent und den Ressourcen\-Editoren, diese Objekte erstellen, wie diese zusammenarbeiten und wie Sie sie in der Programmierung verwenden.  Dokumente, Ansichten und Rahmenfenster werden in [Fensterobjekte](../mfc/window-objects.md) und [Dokument\-\/Ansichtarchitektur](../mfc/document-view-architecture.md) behandelt.  
  
## Siehe auch  
 [Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)