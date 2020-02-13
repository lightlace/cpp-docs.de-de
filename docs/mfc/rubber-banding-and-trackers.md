---
title: Gummibandtechnik und Ziehpunkte
ms.date: 11/04/2016
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
ms.openlocfilehash: 095f3c15546466c6a495f6aa348990ed69b04a9e
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127365"
---
# <a name="rubber-banding-and-trackers"></a>Gummibandtechnik und Ziehpunkte

Ein weiteres Feature, das mit Tracker bereitgestellt wird, ist die "Gummi Bandauswahl", die es Benutzern ermöglicht, mehrere OLE-Elemente auszuwählen, indem Sie ein Größen Rechteck um die auszuwählenden Elemente ziehen. Wenn der Benutzer die linke Maustaste loslässt, werden die Elemente in dem vom Benutzer ausgewählten Bereich ausgewählt und können vom Benutzer bearbeitet werden. Beispielsweise kann der Benutzer die Auswahl in eine andere Containeranwendung ziehen.

Die Implementierung dieser Funktion erfordert zusätzlichen Code in der WM_LBUTTONDOWN Handlerfunktion Ihrer Anwendung.

Im folgenden Codebeispiel werden die Gummi Bandauswahl und zusätzliche Features implementiert.

[!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]

Wenn Sie die rückgängig-Ausrichtung der Tracker während der Gummi Bandbreite zulassen möchten, sollten Sie [CRectTracker:: trackgumband](../mfc/reference/crecttracker-class.md#trackrubberband) aufrufen, wobei der dritte Parameter auf **true**festgelegt ist. Beachten Sie, dass das Zulassen von umkehrbarer Ausrichtung manchmal dazu führt, dass [CRectTracker:: m_rect](../mfc/reference/crecttracker-class.md#m_rect) invertiert wird. Dies kann durch einen [CRect:: NormalizeRect-CRect](../atl-mfc-shared/reference/crect-class.md#normalizerect)-Befehl korrigiert werden.

Weitere Informationen finden Sie unter [Container Client Items](../mfc/containers-client-items.md) und [OLE Drag & Drop: Anpassen von Drag & Drop](../mfc/drag-and-drop-ole.md#customize-drag-and-drop).

## <a name="see-also"></a>Weitere Informationen

[Tracker: Implementieren von Trackern in einer OLE-Anwendung](../mfc/trackers-implementing-trackers-in-your-ole-application.md)<br/>
[CRectTracker-Klasse](../mfc/reference/crecttracker-class.md)
