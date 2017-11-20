---
title: Dokumente, Ansichten und das Framework | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- document templates [MFC], template objects
- applications [MFC]
- MFC, application framework
- application objects [MFC], relation to other MFC objects
- documents [MFC]
- MFC, documents
- document objects [MFC], in relation to other MFC objects
- view objects [MFC], relation to other MFC objects
- MFC, views
- document/view architecture [MFC], about document/view architecture
- objects [MFC], MFC applications
- MFC object relationships
- thread objects [MFC]
ms.assetid: 409ddd9b-66ad-4625-84f7-bf55a41d697b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b6034dc13c554769ab62b37bd1ca143527b5f82e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="documents-views-and-the-framework"></a>Dokumente, Ansichten und das Framework
Das Herzstück des MFC-Frameworks gelten die Konzepte von Dokument und Ansicht in. Ein Dokument ist ein Datenobjekt an, mit denen der Benutzer in einer bearbeitungssitzung interagiert. Wird erstellt, indem die `New` oder **öffnen** Befehl die **Datei** Menü und wird in der Regel in einer Datei gespeichert. (Standard-MFC-Dokumente, die von Klasse abgeleitet **CDocument**, unterscheiden sich von aktive Dokumente und OLE-Verbunddokumente.) Eine Sicht ist ein Fensterobjekt, das über die Interaktion des Benutzers mit einem Dokument.  
  
 Die wichtigsten Objekte in einer ausgeführten Anwendung sind:  
  
-   Das Dokument oder Dokumenten.  
  
     Der Dokumentklasse (abgeleitet [CDocument](../mfc/reference/cdocument-class.md)) gibt an, die Daten Ihrer Anwendung.  
  
     Wenn Sie OLE-Funktionen in Ihrer Anwendung möchten, leiten Sie eine Dokumentklasse von [COleDocument](../mfc/reference/coledocument-class.md) oder einer ihrer abgeleiteten Klassen, je nach Art der Funktionalität, die Sie benötigen.  
  
-   Die Sicht oder Sichten.  
  
     View-Klasse (abgeleitet von [CView](../mfc/reference/cview-class.md)) wird der Benutzer "im Fenster auf die Daten." Die Ansichtsklasse steuert, wie der Benutzer die Daten des Dokuments angezeigt, und mit ihm interagiert. In einigen Fällen sollten Sie ein Dokument mehrere Sichten der Daten enthalten.  
  
     Wenn Sie das Durchführen eines Bildlaufs benötigen, leiten Sie von [CScrollView](../mfc/reference/cscrollview-class.md). Wenn die Sicht eine Benutzeroberfläche, die in einer Dialogfeldvorlagen Ressource angeordnet sind verfügt, abgeleitet [CFormView](../mfc/reference/cformview-class.md). Für einfachen Text-Daten verwenden oder eine Ableitung von [CEditView](../mfc/reference/ceditview-class.md). Bei einer formularbasierten Datenzugriff-Anwendung, z. B. ein Programm Dateneingabe leiten von [CRecordView](../mfc/reference/crecordview-class.md) (für ODBC). Auch werden Klassen [CTreeView](../mfc/reference/ctreeview-class.md), [CListView](../mfc/reference/clistview-class.md), und [CRichEditView](../mfc/reference/cricheditview-class.md).  
  
-   Das Rahmenfenster  
  
     Ansichten werden in "Dokumentrahmenfenster." angezeigt. In einer SDI-Anwendung ist die Dokumentrahmenfenster auch "Hauptrahmenfenster" für die Anwendung. In einer MDI-Anwendung sind Dokumentfenster untergeordnete Fenster in einem Hauptrahmenfenster angezeigt. Ihre Klasse abgeleiteten-Hauptrahmenfenster gibt an, die Formate und andere Merkmale der Rahmenfenster, die Ihre Ansichten enthalten. Wenn Sie Rahmenfenster anpassen müssen, leiten Sie von [CFrameWnd](../mfc/reference/cframewnd-class.md) die Dokumentrahmenfenster für SDI-Anwendungen anpassen. Ableiten von [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) Hauptrahmenfenster für MDI-Anwendungen anpassen. Zudem leiten Sie eine Klasse von [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) , die unterschiedliche Arten von MDI-Dokumentrahmenfenstern anzupassen, die Ihre Anwendung unterstützt.  
  
-   Die Vorlage oder die Vorlagen  
  
     Eine Dokumentvorlage koordiniert die Erstellung der Dokumente, Ansichten und Rahmenfenster. Aus eine bestimmten Dokumentvorlage-Klasse abgeleitet [CDocTemplate](../mfc/reference/cdoctemplate-class.md), erstellt und verwaltet alle geöffneten Dokumente eines bestimmten Typs. Anwendungen, die mehr als einen Typ von Dokument unterstützen haben mehrfache Dokumentvorlagen. Verwenden Sie die Klasse [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) für SDI-Anwendungen oder-Klasse [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) für MDI-Anwendungen.  
  
-   Das Anwendungsobjekt  
  
     Die Anwendungsklasse (abgeleitet von [CWinApp](../mfc/reference/cwinapp-class.md)) steuert alle oben genannten Objekte und gibt an, wie z. B. eine Initialisierung und Bereinigung Anwendungsverhalten. Die Anwendung eine und nur Anwendung-Objekt erstellt und verwaltet die Dokumentvorlagen aus, für jedes Dokument der Anwendung unterstützt werden.  
  
-   Thread-Objekte  
  
     Wenn Ihre Anwendung separaten Ausführungsthreads erstellt wird – beispielsweise, um Berechnungen im Hintergrund ausgeführt – verwenden Sie Klassen abgeleitet [CWinThread](../mfc/reference/cwinthread-class.md). [CWinApp](../mfc/reference/cwinapp-class.md) selbst stammt aus `CWinThread` und den primären Thread (oder die Haupt-Prozess) in der Anwendung darstellt. Sie können auch MFC in sekundären Threads verwenden.  
  
 In einer ausgeführten Anwendung reagieren auf Benutzeraktionen, miteinander verknüpft sind, indem Sie Befehle und anderen Meldungen kooperativ diese Objekte. Ein einzelnes Anwendungsobjekt verwaltet eine oder mehrere Dokumentvorlagen. Jede Dokumentvorlage erstellt und verwaltet eine oder mehrere Dokumente (je nachdem, ob die Anwendung SDI- oder MDI). Der Benutzer anzeigt und bearbeitet ein Dokument über eine Sicht, die in einem Rahmenfenster enthalten sind. Die folgende Abbildung zeigt die Beziehungen zwischen diesen Objekten für eine SDI-Anwendung.  
  
 ![Objekte in einer ausgeführten SDI-Anwendung](../mfc/media/vc386v1.gif "vc386v1")  
Objekte in einer ausgeführten SDI-Anwendung  
  
 Diese Artikelreihe enthält wie die Framework-Tools, die MFC-Anwendung-Assistent und die Ressourcen-Editoren für diese Objekte erstellen, wie diese zusammenarbeiten und wie Sie sie in der Programmierung verwenden. Dokumente, Ansichten und Rahmenfenster werden ausführlicher in [Fensterobjekten](../mfc/window-objects.md) und [Dokument-/Ansichtarchitektur](../mfc/document-view-architecture.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
