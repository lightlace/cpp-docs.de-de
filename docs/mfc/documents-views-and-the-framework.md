---
title: Dokumente, Ansichten und das Framework | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8213ac8d45b2981a7b945fb0af0a590cf7974a8a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402355"
---
# <a name="documents-views-and-the-framework"></a>Dokumente, Ansichten und das Framework

Das Herzstück von MFC-Framework sind Sie die Konzepte von Dokument und Ansicht. Ein Dokument ist ein Datenobjekt in einer bearbeitungssitzung, mit denen der Benutzer interagiert. Er wird erstellt, indem die **neu** oder **öffnen** Befehl die **Datei** im Menü und wird in der Regel in einer Datei gespeichert. (Standard-MFC-Dokumente, die von Klasse abgeleitet `CDocument`, unterscheiden sich von aktive Dokumente und OLE-Dokumenten.) Eine Sicht ist ein Window-Objekt, das über die der Benutzer ein Dokument interagiert.

Die wichtigsten Objekte in einer ausgeführten Anwendung sind:

- Das Dokument oder Dokumenten.

     Die Dokumentklasse (abgeleitet von [CDocument](../mfc/reference/cdocument-class.md)) gibt an, die Daten Ihrer Anwendung.

     Wenn Sie OLE-Funktionen in Ihrer Anwendung möchten, leiten Sie die Dokumentklasse aus [COleDocument](../mfc/reference/coledocument-class.md) oder eine der davon abgeleiteten Klassen verwendet werden, je nach Art der Funktionalität, die Sie benötigen.

- Die Ansicht oder Ansichten.

     Ihr View-Klasse (abgeleitet [CView](../mfc/reference/cview-class.md)) wird der Benutzer "-Fenster auf die Daten." Die Ansichtsklasse steuert, wie der Benutzer die Daten des Dokuments angezeigt, und mit ihm interagiert. In einigen Fällen sollten Sie ein Dokument, um mehrere Ansichten der Daten zu erhalten.

     Wenn Sie das Durchführen eines Bildlaufs benötigen, leiten Sie von [CScrollView](../mfc/reference/cscrollview-class.md). Wenn die Ansicht eine Benutzeroberfläche, die in einer Dialogfeldvorlagen-Ressource angeordnet ist verfügt, leiten Sie von [CFormView](../mfc/reference/cformview-class.md). Klicken Sie für einfachen Text-Daten verwenden, oder ableiten [CEditView](../mfc/reference/ceditview-class.md). Für eine formularbasierte Datenzugriff-Anwendung wie z. B. ein Programm zur Dateneingabe abgeleitet [CRecordView](../mfc/reference/crecordview-class.md) (für ODBC). Auch verfügbar sind Klassen [CTreeView](../mfc/reference/ctreeview-class.md), [CListView](../mfc/reference/clistview-class.md), und [CRichEditView](../mfc/reference/cricheditview-class.md).

- Die Frame-Fensters

     Ansichten werden in "Dokumentrahmenfenster." angezeigt. In einer SDI-Anwendung ist das Dokumentrahmenfenster auch "im Hauptrahmenfenster" für die Anwendung. In einer MDI-Anwendung sind Dokumentfenster untergeordnete Fenster in einem Hauptrahmenfenster angezeigt. Die Klasse abgeleiteten Haupt-Rahmenfenster gibt an, die Stile und andere Merkmale der der Frame-Fensters, die Ihre Ansichten enthalten. Wenn Sie Rahmenfenster anpassen müssen, leiten Sie von [CFrameWnd](../mfc/reference/cframewnd-class.md) der Dokumentrahmenfenster für SDI-Anwendungen anpassen. Leiten Sie von [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) Hauptrahmenfenster für MDI-Anwendungen anpassen. Zudem leiten eine Klasse von [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) , die unterschiedliche Arten von MDI-Dokumentrahmenfenstern anzupassen, die Ihre Anwendung unterstützt.

- Die Dokumentvorlage oder Vorlagen

     Eine Dokumentvorlage orchestriert die Erstellung von Dokumenten, Ansichten und Rahmenfenster. Eine bestimmter Dokumentvorlagen-Klasse, aus der Klasse abgeleiteten [CDocTemplate](../mfc/reference/cdoctemplate-class.md), erstellen und verwalten Sie alle geöffneten Dokumente eines bestimmten Typs. Anwendungen, die mehr als einen Typ des Dokuments zu unterstützen, haben mehrfache Dokumentvorlagen. Verwenden Sie Klasse [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) für SDI-Anwendungen oder Verwendungsklasse [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) für MDI-Anwendungen.

- Das Anwendungsobjekt

     Ihre Anwendungsklasse (abgeleitet [CWinApp](../mfc/reference/cwinapp-class.md)) steuert alle oben genannten Objekte und gibt das Verhalten der Anwendung wie z. B. die Initialisierung und Bereinigung an. Objekt von der Anwendung ein, und nur-Anwendung erstellt und verwaltet die Dokumentvorlagen aus, für jedes Dokument der Anwendung unterstützt werden.

- Thread-Objekte

     Wenn Ihre Anwendung separate Ausführungsthreads erstellt – beispielsweise, um Berechnungen im Hintergrund auszuführen, verwenden Sie Klassen, die von [CWinThread](../mfc/reference/cwinthread-class.md). [CWinApp](../mfc/reference/cwinapp-class.md) selbst stammt aus `CWinThread` und den primären Thread der Ausführung (oder der Hauptprozess) in Ihrer Anwendung darstellt. Sie können auch MFC in sekundären Threads verwenden.

In einer ausgeführten Anwendung reagieren auf Benutzeraktionen, eine gemeinsame von Befehlen und anderen Nachrichten verbunden sind kooperativ diese Objekte. Eine einzelne Application-Objekt verwaltet einen oder mehrere Dokumentvorlagen. Jede Dokumentvorlage erstellt und verwaltet eine oder mehrere Dokumente (je nachdem, ob die Anwendung SDI- oder MDI). Der Benutzer Ansichten und bearbeitet ein Dokument über eine Sicht, die in einem Rahmenfenster enthalten sind. Die folgende Abbildung zeigt die Beziehungen zwischen diesen Objekten für einer SDI-Anwendung.

![Objekte in einer ausgeführten SDI-Anwendung](../mfc/media/vc386v1.gif "vc386v1") Objekte in einer ausgeführten SDI-Anwendung

Die restlichen in dieser Artikelreihe wird erläutert, wie die Framework-Tools, den Assistenten zum MFC-Anwendungen und die Ressourcen-Editoren, die diese Objekte erstellen, wie diese zusammenarbeiten und wie Sie sie bei der Programmierung verwenden. Dokumente, Ansichten und Rahmenfenster werden ausführlicher in [Fensterobjekte](../mfc/window-objects.md) und [Dokument-/Ansichtarchitektur](../mfc/document-view-architecture.md).

## <a name="see-also"></a>Siehe auch

[Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
