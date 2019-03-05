---
title: Dokumentklassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.document
helpviewer_keywords:
- document classes [MFC]
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
ms.openlocfilehash: a7034a99bfefe8f4c11cdf8f99dc4b0c31fac10a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289714"
---
# <a name="document-classes"></a>Dokumentklassen

Dokument-Klasse, von erstellten Objekte Dokumentvorlage Objekte, verwalten, die Daten der Anwendung. Sie werden eine Klasse für die Dokumente aus einer dieser Klassen ableiten.

Dokument-Klassenobjekten interagieren mit Objekte anzeigen. Ansichtsobjekte den Clientbereich eines Fensters darstellen, Anzeigen von Daten eines Dokuments und Benutzern, die Sie mit ihm interagieren. Dokumente und Ansichten werden von einer Dokumentvorlage Objekt erstellt.

[CDocument](../mfc/reference/cdocument-class.md)<br/>
Die Basisklasse für anwendungsspezifische Dokumente. Leiten Sie Ihre "Document"-Klasse oder die Klassen aus `CDocument`.

[COleDocument](../mfc/reference/coledocument-class.md)<br/>
Für Verbunddokument-Implementierung als auch einfache Container-Unterstützung verwendet. Dient als Container für Klassen abgeleitet [CDocItem](../mfc/reference/cdocitem-class.md). Diese Klasse kann als Basisklasse verwendet werden, für Container dokumentiert und die Basisklasse für ist `COleServerDoc`.

[COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)<br/>
Eine abgeleitete Klasse `COleDocument` , die für die Verknüpfung stellt die Infrastruktur bereit. Sie sollten die Document-Klassen ableiten, für Ihre containeranwendungen von dieser Klasse statt von `COleDocument` , wenn Sie Links auf eingebettete Objekte unterstützen sollen.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Die Liste der OLE-Client-Elemente, die im rich-Edit-Steuerelement verwaltet. Mit verwendet [CRichEditView](../mfc/reference/cricheditview-class.md) und [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).

[COleServerDoc](../mfc/reference/coleserverdoc-class.md)<br/>
Als die Basisklasse verwendet für Serveranwendung Document-Klassen. `COleServerDoc` Objekte stellen den größten Teil der Unterstützung durch Interaktionen mit Server [COleServerItem](../mfc/reference/coleserveritem-class.md) Objekte. Visual Bearbeitungsfunktionen unter Verwendung der Klassenbibliothek Dokument-/Ansichtarchitektur bereitgestellt.

[CHtmlEditDoc](../mfc/reference/chtmleditdoc-class.md)<br/>
Bereitstellt, mit [CHtmlEditView](../mfc/reference/chtmleditview-class.md), die Funktionalität der WebBrowser HTML-Bearbeitung Plattform im Kontext der MFC Dokument-/ Ansichtarchitektur.

## <a name="related-classes"></a>Verwandte Klassen

Document-Klasse-Objekte können dauerhaft sein – das heißt, sie es wieder zu lesen und Schreiben Sie ihren Status auf einem Speichermedium können. MFC stellt die `CArchive` Klasse, um zu ermöglichen, die Daten des Dokuments auf einem Speichermedium übertragen.

[CArchive](../mfc/reference/carchive-class.md)<br/>
Arbeitet mit einem [CFile](../mfc/reference/cfile-class.md) Objekt das Implementieren des permanenten Speicher für Objekte, die über die Serialisierung (finden Sie unter [CObject:: Serialize](../mfc/reference/cobject-class.md#serialize)).

Dokumente können auch OLE-Objekte enthalten. `CDocItem` ist die Basisklasse der Server- und Elemente.

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
Abstrakte Basisklasse von [COleClientItem](../mfc/reference/coleclientitem-class.md) und [COleServerItem](../mfc/reference/coleserveritem-class.md). Objekte der Klassen abgeleitet `CDocItem` Teilen von Dokumenten darstellen.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
