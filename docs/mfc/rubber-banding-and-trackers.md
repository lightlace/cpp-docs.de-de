---
title: Gummibandtechnik und Ziehpunkte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- trackers [MFC]
- CRectTracker class [MFC], implementing trackers
- OLE objects [MFC], selecting
- rubber banding [MFC]
- WM_LBUTTONDOWN [MFC]
ms.assetid: 0d0fa64c-6418-4baf-ab7f-2d16ca039230
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2b1b5b0a49fdb59417be04864c9d1ef5341f849
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="rubber-banding-and-trackers"></a>Gummibandtechnik und Ziehpunkte
Eine weitere Funktion, die im Lieferumfang von Trackern ist die Auswahl "Kunststoff-Band-", die einem Benutzer ermöglicht, mehrere OLE-Elemente auswählen, durch Ziehen eines Rechtecks anpassen, um die Elemente ausgewählt werden. Wenn der Benutzer die linke Maustaste loslässt, Elemente innerhalb des Bereichs, der vom Benutzer ausgewählten markiert sind, und Sie werden vom Benutzer bearbeitet werden können. Beispielsweise kann der Benutzer die Auswahl in einem anderen Steuerelementcontainer-Anwendung ziehen.  
  
 Diese Funktion erfordert zusätzlichen Code in Ihrer Anwendungsverzeichnis `WM_LBUTTONDOWN` Handlerfunktion.  
  
 Das folgende Codebeispiel implementiert Kunststoff-Band-Auswahl und zusätzliche Funktionen.  
  
 [!code-cpp[NVC_MFCOClient#6](../mfc/codesnippet/cpp/rubber-banding-and-trackers_1.cpp)]  
  
 Wenn Sie umkehrbare Ausrichtung Tracker während Gummibandtechnik zulassen möchten, sollten Sie aufrufen [CRectTracker::TrackRubberBand](../mfc/reference/crecttracker-class.md#trackrubberband) mit dem dritten Parameter festgelegt **"true"**. Beachten Sie, dass ermöglicht umkehrbare Ausrichtung in einigen Fällen bewirkt [CRectTracker::m_rect](../mfc/reference/crecttracker-class.md#m_rect) , umgekehrt werden. Dies kann behoben werden, durch den Aufruf von [CRect:: NormalizeRect](../atl-mfc-shared/reference/crect-class.md#normalizerect).  
  
 Weitere Informationen finden Sie unter [Containerclientelemente](../mfc/containers-client-items.md) und [Anpassen von Drag & Drop](../mfc/drag-and-drop-customizing.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Tracker: Implementieren von Trackern in der OLE-Anwendung](../mfc/trackers-implementing-trackers-in-your-ole-application.md)   
 [CRectTracker-Klasse](../mfc/reference/crecttracker-class.md)
