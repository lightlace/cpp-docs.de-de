---
title: OLE-Containerklassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e17161340881bb53601bc04dce6f5e375f746b02
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404708"
---
# <a name="ole-container-classes"></a>OLE-Containerklassen

Diese Klassen werden von containeranwendungen verwendet. Beide `COleLinkingDoc` und `COleDocument` Verwalten von Sammlungen `COleClientItem` Objekte. Anstatt die Dokumentklasse von ableiten `CDocument`, müssen Sie leiten Sie ihn von `COleLinkingDoc` oder `COleDocument`, abhängig davon, ob Sie die Unterstützung für Links zu Objekten, die in ein Dokument eingebettete möchten.

Verwenden einer `COleClientItem` Objekt, das jeden OLE-Element im Dokument darstellt, die aus einem anderen Dokument eingebettet ist oder einen Link zu einem anderen Dokument.

[COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)<br/>
Active Document-Container wird unterstützt.

[COleDocument-Klasse](../mfc/reference/coledocument-class.md)<br/>
Für Verbunddokument-Implementierung als auch einfache Container-Unterstützung verwendet. Dient als Container für Klassen abgeleitet `CDocItem`. Diese Klasse kann als Basisklasse verwendet werden, für Container dokumentiert und die Basisklasse für ist `COleServerDoc`.

[COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)<br/>
Eine abgeleitete Klasse `COleDocument` , die für die Verknüpfung stellt die Infrastruktur bereit. Sie sollten die Document-Klassen ableiten, für Ihre containeranwendungen von dieser Klasse statt von `COleDocument` , wenn Sie Links auf eingebettete Objekte unterstützen sollen.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Die Liste der OLE-Client-Elemente, die im rich-Edit-Steuerelement verwaltet. Mit verwendet [CRichEditView](../mfc/reference/cricheditview-class.md) und [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
Abstrakte Basisklasse von `COleClientItem` und `COleServerItem`. Objekte der Klassen abgeleitet `CDocItem` Teilen von Dokumenten darstellen.

[COleClientItem](../mfc/reference/coleclientitem-class.md)<br/>
Eine Client-Element-Klasse, die Clientseite der Verbindung mit einer eingebetteten oder verknüpften OLE-Element darstellt. Der Clientelemente werden von dieser Klasse ableiten.

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
Bietet eine clientseitige-Zugriff auf ein Element in einem rich-Edit-Steuerelement, bei der Verwendung mit gespeicherten OLE `CRichEditView` und `CRichEditDoc`.

[COleException](../mfc/reference/coleexception-class.md)<br/>
Eine Ausnahme, die nach einem Fehler bei der Verarbeitung von OLE. Diese Klasse wird von sowohl Container und Server verwendet.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)

