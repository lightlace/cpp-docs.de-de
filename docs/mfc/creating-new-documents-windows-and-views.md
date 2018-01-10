---
title: Erstellen neuer Dokumente, Fenster und Ansichten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MDI [MFC], creating windows
- window objects [MFC], creating
- objects [MFC], creating document objects
- MFC default objects
- frame windows [MFC], creating
- windows [MFC], MDI
- MFC, documents
- view objects [MFC], creating
- windows [MFC], creating
- overriding, default view behavior
- views [MFC], initializing
- customizing MFC default objects
- MFC, frame windows
- MFC, views
- MDI [MFC], frame windows
- child windows [MFC], creating MDI
- view objects [MFC]
- document objects [MFC], creating
- MFC default objects [MFC], customizing
- views [MFC], overriding default behavior
- initializing views [MFC]
ms.assetid: 88aa1f5f-2078-4603-b16b-a2b4c7b4a2a3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 01837b079ba08ea2961b141549476da11a481a0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-new-documents-windows-and-views"></a>Erstellen neuer Dokumente, Fenster und Ansichten
Die folgenden Abbildungen erhalten einen Überblick der Erstellungsvorgang für Dokumente, Ansichten und Rahmenfenster. Anderen Artikeln, die für die beteiligten Objekte zu konzentrieren. angeben Weitere Details.  
  
 Nach Abschluss dieses Vorgangs wird die kooperierender Objekte vorhanden sind, und Speichern von Zeigern miteinander. Die folgenden Abbildungen zeigen die Reihenfolge, in der Objekte erstellt werden. Sie können die Sequenz von Abbildung zu Abbildung entsprechen.  
  
 ![Sequenz für die Erstellung eines Dokuments](../mfc/media/vc387l1.gif "vc387l1")  
Reihenfolge beim Erstellen eines Dokuments  
  
 ![Frame-Fenster bei der Fenstererstellung](../mfc/media/vc387l2.png "vc387l2")  
Reihenfolge beim Erstellen eines Rahmenfensters  
  
 ![Sequenz für die Erstellung einer Sicht](../mfc/media/vc387l3.gif "vc387l3")  
Reihenfolge beim Erstellen einer Ansicht  
  
 Informationen dazu, wie das Framework die neues Dokument, Ansicht und Rahmenfensterobjekt initialisiert, finden Sie in den Klassen [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), und [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) in der Verweis auf die MFC-Bibliothek. Siehe auch [technischen Hinweis 22](../mfc/tn022-standard-commands-implementation.md), dort die Erstellung und Initialisierung Prozesse weiter, unter dessen Erläuterung von Standardbefehlen, das Framework für die `New` und **öffnen** Elemente auf der **Datei** Menü.  
  
##  <a name="_core_initializing_your_own_additions_to_these_classes"></a>Initialisieren Ihre eigenen Ergänzungen für diese Klassen  
 Die vorhergehenden Abbildungen empfehlen auch die Punkte, an denen Sie, Memberfunktionen überschreiben können, um Ihre Anwendung Objekte zu initialisieren. Eine Überschreibung der `OnInitialUpdate` in Ihrer Ansicht Klasse ist die beste Stelle, um die Ansicht zu initialisieren. Die `OnInitialUpdate` Aufruf erfolgt sofort, nachdem das Rahmenfenster erstellt wird und die Ansicht im Rahmenfenster an sein Dokument angefügt ist. Angenommen, Ihre Ansicht einer Bildlaufleiste ist (abgeleitet `CScrollView` anstelle `CView`), sollten Sie die Größe der Ansicht basierend auf die Dokumentgröße in Festlegen Ihrer `OnInitialUpdate` außer Kraft setzen. (Dieser Prozess wird in der Beschreibung der Klasse beschrieben [CScrollView](../mfc/reference/cscrollview-class.md).) Sie können außer Kraft setzen die **CDocument** Memberfunktionen `OnNewDocument` und `OnOpenDocument` anwendungsspezifische Initialisierung des Dokuments angeben. In der Regel müssen Sie beide überschreiben, da ein Dokument auf zwei Arten erstellt werden kann.  
  
 In den meisten Fällen sollten Ihre Überschreibung die Basisklassenversion aufrufen. Weitere Informationen finden Sie unter den benannten Memberfunktionen von Klassen [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), und [CWinApp](../mfc/reference/cwinapp-class.md) in MFC Bibliotheksverweis.  
  
## <a name="see-also"></a>Siehe auch  
 [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md)   
 [Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)   
 [Beziehungen zwischen MFC-Objekten](../mfc/relationships-among-mfc-objects.md)

