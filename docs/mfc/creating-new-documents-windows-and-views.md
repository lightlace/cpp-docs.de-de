---
title: Erstellen neuer Dokumente, Fenster und Ansichten
ms.date: 11/19/2018
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
ms.openlocfilehash: 57e558848ce76a7c74b5715529661ad24c9cbb8e
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175391"
---
# <a name="creating-new-documents-windows-and-views"></a>Erstellen neuer Dokumente, Fenster und Ansichten

Die folgenden Abbildungen geben einen Überblick über der Erstellungsvorgang für Dokumente, Ansichten und Rahmenfenster. Weitere Artikel, die sich auf die beteiligten Objekte konzentrieren bieten weitere Details.

Nach Abschluss dieses Prozesses die kooperierender Objekte vorhanden, und Speichern von Zeigern miteinander. Die folgenden Abbildungen zeigen die Sequenz, in der Objekte erstellt werden. Sie können die Sequenz von Abbildung zu Abbildung folgen.

![Sequenz für die Erstellung eines Dokuments](../mfc/media/vc387l1.gif "Sequenz für die Erstellung eines Dokuments") <br/>
Reihenfolge beim Erstellen eines Dokuments

![Frame-Fenster bei der Fenstererstellung](../mfc/media/vc387l2.png "Frame-Fenster bei der Fenstererstellung") <br/>
Reihenfolge beim Erstellen eines Rahmenfensters

![Sequenz zum Erstellen einer Ansicht](../mfc/media/vc387l3.gif "Sequenz zum Erstellen einer Ansicht") <br/>
Reihenfolge beim Erstellen einer Ansicht

Informationen wie das Framework für das neue Dokument, Ansicht und Rahmenfenster Objekte initialisiert werden, finden Sie unter Klassen [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), und [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) in der MFC-Bibliothek-Referenz. Siehe auch [technischen Hinweis 22](../mfc/tn022-standard-commands-implementation.md), dem erläutert wird, die Erstellung und Initialisierung Prozesse weiter unter der Erläuterung der des Frameworks-Standardbefehle für die **neu** und **Öffnen** Elemente auf der **Datei** Menü.

##  <a name="_core_initializing_your_own_additions_to_these_classes"></a> Initialisieren Ihre eigenen Ergänzungen auf diese Klassen

Die vorhergehenden Abbildungen empfiehlt es sich auch um die Punkte, an denen Sie die Memberfunktionen zum Initialisieren von Objekten der Anwendung überschreiben können. Eine Überschreibung der `OnInitialUpdate` in der Ansicht-Klasse ist der beste Ort für die Ansicht zu initialisieren. Die `OnInitialUpdate` Aufruf erfolgt, sobald das Rahmenfenster erstellt wird und die Ansicht im Rahmenfenster sein Dokument angefügt ist. Wenn Ihrer Ansicht einen Bildlauf ist z. B. (abgeleitet `CScrollView` statt `CView`), sollten Sie festlegen, die Größe der Ansicht basierend auf der Größe des Dokuments in Ihre `OnInitialUpdate` außer Kraft setzen. (Dieser Prozess wird beschrieben, in der Beschreibung der Klasse [CScrollView](../mfc/reference/cscrollview-class.md).) Können Sie überschreiben die `CDocument` Memberfunktionen `OnNewDocument` und `OnOpenDocument` anwendungsspezifische Initialisierung des Dokuments angeben. In der Regel müssen Sie beide überschreiben, da ein Dokument auf zwei Arten erstellt werden kann.

In den meisten Fällen sollten Ihre Überschreibung die Basisklassenversion aufrufen. Weitere Informationen finden Sie auf die benannte Memberfunktionen von Klassen [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), [CFrameWnd](../mfc/reference/cframewnd-class.md), und [CWinApp](../mfc/reference/cwinapp-class.md) in die MFC-Bibliothek Bibliotheksreferenz.

## <a name="see-also"></a>Siehe auch

[Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md)<br/>
[Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)<br/>
[Beziehungen zwischen MFC-Objekten](../mfc/relationships-among-mfc-objects.md)

