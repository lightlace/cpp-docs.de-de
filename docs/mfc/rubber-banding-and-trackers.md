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
ms.openlocfilehash: a6a9c9848e21129d4e6a8ce300e8750b4a0c6126
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281043"
---
# <a name="rubber-banding-and-trackers"></a>Gummibandtechnik und Ziehpunkte

Ein weiteres Feature, mit Tracker ist die "-" Gummibandauswahl, die einem Benutzer ermöglicht, mehrere OLE-Elemente auswählen, indem Sie ziehen ein Rechteck zur größenanpassung für die Elemente ausgewählt werden. Wenn der Benutzer die linke Maustaste loslässt, Elemente in der Region, die vom Benutzer ausgewählten ausgewählt sind, und können vom Benutzer bearbeitet werden. Beispielsweise kann der Benutzer die Auswahl in eine andere containeranwendung ziehen.

Implementieren dieses Feature erfordert zusätzlichen Code in Ihrer Anwendung WM_LBUTTONDOWN Handler-Funktion.

Das folgende Codebeispiel implementiert die Gummibandauswahl- und zusätzliche Features.

[!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]

Wenn Sie rückgängig gemacht werden Ausrichtung der nachverfolgung während der Gummibandtechnik zulassen möchten, sollten Sie aufrufen [CRectTracker::TrackRubberBand](../mfc/reference/crecttracker-class.md#trackrubberband) mit den dritten Parameter auf **"true"**. Beachten Sie, dass rückgängig gemacht werden Ausrichtung ermöglicht in einigen Fällen bewirkt [CRectTracker::m_rect](../mfc/reference/crecttracker-class.md#m_rect) umgekehrt werden. Dies kann korrigiert werden, durch einen Aufruf von [CRect:: NormalizeRect](../atl-mfc-shared/reference/crect-class.md#normalizerect).

Weitere Informationen finden Sie unter [Containerclientelemente](../mfc/containers-client-items.md) und [Anpassen von Drag & Drop](../mfc/drag-and-drop-customizing.md).

## <a name="see-also"></a>Siehe auch

[Tracker: Implementieren von Trackern in einer OLE-Anwendung](../mfc/trackers-implementing-trackers-in-your-ole-application.md)<br/>
[CRectTracker-Klasse](../mfc/reference/crecttracker-class.md)
