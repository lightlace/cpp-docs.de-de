---
title: Optimieren der Steuerelementdarstellung
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
ms.openlocfilehash: 4d0037ebdfe56690be2f18a2790b2b13967e337c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378311"
---
# <a name="optimizing-control-drawing"></a>Optimieren der Steuerelementdarstellung

Wenn ein Steuerelement angewiesen wird, um sich selbst in einem Container bereitgestellten Gerätekontext zu zeichnen, in der Regel GDI-Objekte (z. B. Stifte, Pinseln und Schriftarten) in den Gerätekontext auswählt, führt seine Zeichenvorgänge und stellt die vorherigen GDI-Objekte. Wenn der Container enthält mehrere Steuerelemente, die in den gleichen Gerätekontext gezeichnet werden soll, und jedes Steuerelement wählt die GDI-Objekte, die erfordert, kann Zeit gespeichert werden, wenn die Steuerelemente zuvor ausgewählten Objekte nicht einzeln wiederherstellen. Nachdem alle Steuerelemente gezeichnet wurden, kann die Container automatisch die ursprünglichen Objekte wiederherstellen.

Um zu erkennen, ob ein Container diese Technik unterstützt, kann ein Steuerelement Aufrufen der [COleControl::IsOptimizedDraw](../mfc/reference/colecontrol-class.md#isoptimizeddraw) Member-Funktion. Wenn diese Funktion gibt **"true"**, das Steuerelement kann den normalen Schritt der Wiederherstellung der zuvor ausgewählten Objekte überspringen.

Betrachten Sie ein Steuerelement, das Folgendes (nicht optimierte) muss `OnDraw` Funktion:

[!code-cpp[NVC_MFC_AxOpt#15](../mfc/codesnippet/cpp/optimizing-control-drawing_1.cpp)]

Stift und Pinsel in diesem Beispiel werden lokale Variablen, d. h., deren Destruktoren aufgerufen werden, wenn sie den gültigen Bereich verlassen (wenn die `OnDraw` Funktion enden). Die Destruktoren versucht, die die entsprechenden GDI-Objekte zu löschen. Aber sie sollten nicht gelöscht werden, wenn Sie planen, lassen Sie in den Gerätekontext Seitenbildlaufposition nach aktivierten `OnDraw`.

Um zu verhindern, dass die [CPen](../mfc/reference/cpen-class.md) und [CBrush](../mfc/reference/cbrush-class.md) Objekte zerstört wird, wenn `OnDraw` abgeschlossen ist, in der Membervariablen anstelle von lokalen Variablen speichern. Fügen Sie in der Klassendeklaration des Steuerelements Deklarationen für zwei neue Membervariablen hinzu:

[!code-cpp[NVC_MFC_AxOpt#16](../mfc/codesnippet/cpp/optimizing-control-drawing_2.h)]
[!code-cpp[NVC_MFC_AxOpt#17](../mfc/codesnippet/cpp/optimizing-control-drawing_3.h)]

Anschließend wird die `OnDraw` Funktion kann wie folgt umgeschrieben werden:

[!code-cpp[NVC_MFC_AxOpt#18](../mfc/codesnippet/cpp/optimizing-control-drawing_4.cpp)]

Dadurch wird verhindert, dass der Stift und Pinsel jedes Mal `OnDraw` aufgerufen wird. Die Verbesserung der Geschwindigkeit wird auf Kosten der zusätzliche Daten zu verwalten.

Wenn die ForeColor oder BackColor-Eigenschaft geändert wird, muss der Stift oder Pinsel neu erstellt werden. Überschreiben Sie zu diesem Zweck die [Memberfunktionen OnForeColorChanged](../mfc/reference/colecontrol-class.md#onforecolorchanged) und [OnBackColorChanged](../mfc/reference/colecontrol-class.md#onbackcolorchanged) Memberfunktionen:

[!code-cpp[NVC_MFC_AxOpt#19](../mfc/codesnippet/cpp/optimizing-control-drawing_5.cpp)]

Abschließend, beseitigen unnötigen `SelectObject` Aufrufe ändern `OnDraw` wie folgt:

[!code-cpp[NVC_MFC_AxOpt#20](../mfc/codesnippet/cpp/optimizing-control-drawing_6.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)<br/>
[COleControl-Klasse](../mfc/reference/colecontrol-class.md)<br/>
[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md)<br/>
[MFC-ActiveX-Steuerelemente: Darstellen eines ActiveX-Steuerelements](../mfc/mfc-activex-controls-painting-an-activex-control.md)
