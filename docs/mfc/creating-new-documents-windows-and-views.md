---
title: "Erstellen neuer Dokumente, Fenster und Ansichten | Microsoft Docs"
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
  - "Untergeordnete Fenster, Erstellen von MDI"
  - "Anpassen der MFC-Standardobjekte"
  - "Document-Objekte, Erstellen"
  - "Rahmenfenster [C++], Erstellen"
  - "Initialisieren von Ansichten"
  - "MDI [C++], Erstellen von Fenstern"
  - "MDI [C++], Rahmenfenster"
  - "MFC [C++], Dokumente"
  - "MFC [C++], Rahmenfenster"
  - "MFC [C++], Ansichten"
  - "MFC-Standardobjekte"
  - "MFC-Standardobjekte, Anpassen"
  - "Objekte [C++], Erstellen von Dokumentobjekten"
  - "Überschreiben, Standardansichtsverhalten"
  - "View-Objekte"
  - "View-Objekte, Erstellen"
  - "Ansichten [C++], Initialisieren"
  - "Ansichten [C++], Überschreiben von Standardverhalten"
  - "Fensterobjekte [C++], Erstellen"
  - "Fenster [C++], Erstellen"
  - "Fenster [C++], MDI"
ms.assetid: 88aa1f5f-2078-4603-b16b-a2b4c7b4a2a3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Erstellen neuer Dokumente, Fenster und Ansichten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Abbildungen geben eine Übersicht des Erstellungsprozesses für Dokumente, Ansichten und Rahmenfenster.  Andere Elemente, die auf die beteiligten Objekte konzentrieren, werden Details fest.  
  
 Bei Beendigung dieses Prozesses vorhanden sind sich kooperierende Objekte und speichern Zeiger miteinander.  Die folgenden Abbildungen zeigen die Reihenfolge, in der Objekte erstellt werden.  Sie können die Reihenfolge der Abbildung zu Abbildung folgen.  
  
 ![Sequenz für die Erstellung eines Dokuments](../mfc/media/vc387l1.png "vc387L1")  
Reihenfolge beim Erstellen eines Dokuments  
  
 ![Reihenfolge der Rahmenfenstererstellung](../mfc/media/vc387l2.png "vc387L2")  
Reihenfolge beim Erstellen eines Rahmenfensters  
  
 ![Sequenz für die Erstellung einer Ansicht](../mfc/media/vc387l3.png "vc387L3")  
Reihenfolge beim Erstellen einer Ansicht  
  
 Informationen darüber, wie das Framework das neue Dokument, die Ansicht und die Rahmenfensterobjekte initialisiert, finden Sie Klassen [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) und [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) in der MFC\-Bibliotheksreferenz.  Siehe auch [Technischer Hinweis 22](../mfc/tn022-standard-commands-implementation.md), das die Erstellung und die Initialisierungsprozesse weiter unter ihrer Erläuterung die Standardbefehle des Frameworks für die `New` und **Öffnen**\-Elemente im Menü **Datei** erläutert.  
  
##  <a name="_core_initializing_your_own_additions_to_these_classes"></a> Initialisieren eigener Hinzufügungen zu diesen Klassen  
 Die vorangehenden Abbildungen werden auch die Punkte vor, mit denen Sie Memberfunktionen überschreiben können, um die Objekte der Anwendung initialisiert.  Eine Überschreibung von `OnInitialUpdate` in der Ansichtsklasse ist der optimale Ort, das der Ansicht zu initialisieren.  Der Aufruf `OnInitialUpdate` tritt auf, nachdem das Rahmenfenster erstellt und die Ansicht innerhalb des Rahmenfensters zum Dokument angefügt ist.  Wenn die Ansicht einer Bildlaufansicht \(abgeleitet von `CScrollView` statt `CView`\) ist, sollten Sie die Ansichtsgröße auf Grundlage der Dokumentgröße in der Überschreibung `OnInitialUpdate` festlegen. \(Dieser Prozess wird in der Beschreibung der [CScrollView](../mfc/reference/cscrollview-class.md) beschrieben.\) Sie können die **CDocument**\-Memberfunktionen `OnNewDocument` und `OnOpenDocument` überschreiben, um anwendungsspezifische Initialisierung des Dokuments bereitzustellen.  In der Regel müssen Sie beide überschreiben, da ein Dokument auf zwei Weisen erstellt werden kann.  
  
 In den meisten Fällen sollte die Überschreibung die Basisklassenversion aufrufen.  Weitere Informationen finden Sie auf die benannten Memberfunktionen von Klassen [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md) und [CWinApp](../mfc/reference/cwinapp-class.md) in der MFC\-Bibliotheksreferenz.  
  
## Siehe auch  
 [Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md)   
 [Erstellen von Dokument\/Ansicht](../mfc/document-view-creation.md)   
 [Beziehungen zwischen MFC\-Objekten](../mfc/relationships-among-mfc-objects.md)