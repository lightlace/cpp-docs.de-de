---
title: 'Drag & Drop: Implementieren eines Drop-Ziels'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE drag and drop [MFC], implementing drop targets
- OLE drag and drop [MFC], drop target
- drag and drop [MFC], drop target
ms.assetid: 0689f1ec-5326-4008-b226-4b373c881358
ms.openlocfilehash: 46501193569d7f3098e23c67c68c76ce20a82ea3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405936"
---
# <a name="drag-and-drop-implementing-a-drop-target"></a>Drag & Drop: Implementieren eines Drop-Ziels

In diesem Artikel wird beschrieben, wie Sie Ihre Anwendung ein Ablageziel zu machen. Implementieren ein Ablageziel erfordert etwas mehr Arbeit als die Implementierung einer Drop-Quelle, aber es ist immer noch relativ einfach. Diese Techniken gelten auch für nicht-OLE-Anwendungen verwendet werden.

#### <a name="to-implement-a-drop-target"></a>Um ein Ablageziel zu implementieren.

1. Fügen Sie eine Membervariable zu den einzelnen Sichten in der Anwendung, die ein Ablageziel sein sollen. Diese Membervariable muss vom Typ `COleDropTarget` oder eine Klasse abgeleitet wird.

1. Aus Ihrer Ansichtsklasse-Funktion, die verarbeitet die **WM_CREATE** Nachricht (in der Regel `OnCreate`), rufen Sie der neue Membervariable `Register` Member-Funktion. `Revoke` wird automatisch für Sie aufgerufen werden, wenn die Ansicht zerstört wird.

1. Überschreiben Sie die folgenden Funktionen. Wenn Sie das gleiche Verhalten in der gesamten Anwendung möchten, überschreiben Sie diese Funktionen in Ihrer Ansichtsklasse. Sollten Sie Verhalten in einzelnen Fällen ändern oder zu aktivieren, löschen Sie für nicht-möchten`CView` Windows, überschreiben Sie diese Funktionen in Ihre `COleDropTarget`-abgeleitete Klasse.

    |außer Kraft setzen|Um zu ermöglichen|
    |--------------|--------------|
    |`OnDragEnter`|Löschen Sie im Fenster erfolgen. Wird aufgerufen, wenn der Cursor zuerst das Fenster betritt.|
    |`OnDragLeave`|Besonderes Verhalten, wenn der Ziehvorgang des angegebenen Fensters verlässt.|
    |`OnDragOver`|Löschen Sie im Fenster erfolgen. Aufgerufen, wenn der Cursor über das Fenster gezogen wird.|
    |`OnDrop`|Behandlung von Daten in das angegebene Fenster gelöscht wird.|
    |`OnScrollBy`|Spezielles Verhalten für die beim Durchführen eines Bildlaufs erforderlich im Zielfenster ist.|

Finden Sie in der Datei MAINVIEW. CPP-Datei, die MFC-OLE-Beispiel [OCLIENT](../overview/visual-cpp-samples.md) für verdeutlicht, wie diese Funktionen zusammen verwendet werden.

Weitere Informationen finden Sie unter:

- [Implementieren einer Drop-Quelle](../mfc/drag-and-drop-implementing-a-drop-source.md)

- [Erstellen und Zerstören von OLE-Datenobjekte und Datenquellen](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [Bearbeiten von OLE-Datenobjekte und Datenquellen](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="see-also"></a>Siehe auch

[Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md)<br/>
[COleDropTarget-Klasse](../mfc/reference/coledroptarget-class.md)
