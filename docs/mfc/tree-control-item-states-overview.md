---
title: Übersicht über Elementzustände des Struktursteuerung-Steuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- states, CTreeCtrl items
- tree controls [MFC], item states overview
- CTreeCtrl class [MFC], item states
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
ms.openlocfilehash: 57c6714073f4939ffb791a78454e9eac6342309b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392465"
---
# <a name="tree-control-item-states-overview"></a>Übersicht über Elementzustände des Struktursteuerung-Steuerelements

Jedes Element in einem Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) verfügt über einen aktuellen Zustand. Beispielsweise kann ein Element werden, deaktiviert ist, erweitert, und so weiter ausgewählt. Zum größten Teil, legt das Strukturansicht-Steuerelement automatisch den Zustand eines Elements entsprechend Benutzeraktionen, wie z. B. Auswahl eines Elements fest. Sie können auch den Zustand eines Elements festlegen, mit der [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate) Member-Funktion und rufen Sie den aktuellen Status eines Elements mithilfe der [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate) Member-Funktion. Eine vollständige Liste der Element-Zustände, finden Sie unter [Strukturansicht Steuerelement Konstanten](/windows/desktop/Controls/tree-view-control-item-states) im Windows SDK.

Aktuellen Status eines Elements wird angegeben, indem die *nState* Parameter. Ein Strukturansicht-Steuerelement kann den Zustand eines Elements eine Benutzereingabe, wie Sie das Element auswählen, oder Festlegen des Fokus auf das Element entsprechend ändern. Darüber hinaus kann eine Anwendung den Zustand eines Elements zu deaktivieren oder das Element auszublenden oder die Angabe ein Overlaybild oder das Zustandsbild ändern.

Wenn Sie festlegen oder ändern den Zustand eines Elements, das *nStateMask* Parameter gibt an, welcher Status bits festgelegt ist, und die *nState* Parameter enthält die neuen Werte für diese Komponenten. Beispielsweise das folgende Beispiel ändert den aktuellen Status eines übergeordneten Elements (angegeben durch *hParentItem*) in einer `CTreeCtrl` Objekt (`m_treeCtrl`) zu `TVIS_EXPANDPARTIAL`:

[!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]

Ein weiteres Beispiel für das Ändern des Status wäre eines Elements Überlagerungsbild festgelegt. Um dies zu erreichen *nStateMask* muss enthalten der `TVIS_OVERLAYMASK` Wert und *nState* muss den einsbasierte Index das Überlagerungsbild verschoben acht Bits mit Links enthalten die [ INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) Makro. Der Index kann es sich um 0 kein Overlaybild an sein. Das Überlagerungsbild muss hinzugefügt worden sein das Strukturansicht-Steuerelement-Liste mit den Overlay-Images von einem vorherigen Aufruf von der [CImageList:: SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) Funktion. Die Funktion gibt den einsbasierten Index des Bildes, das Hinzufügen an; Dies ist der Index, der mit dem Makro INDEXTOOVERLAYMASK verwendet. Ein Strukturansicht-Steuerelement kann bis zu vier Overlaybilder haben.

Festlegen des statusbilds eines Elements, *nStateMask* muss enthalten der `TVIS_STATEIMAGEMASK` Wert und *nState* muss den einsbasierten Index der Zustandsgrafik verschoben 12 Bits mit Links enthalten die [ INDEXTOSTATEIMAGEMASK](/windows/desktop/api/commctrl/nf-commctrl-indextostateimagemask) Makro. Der Index kann es sich um 0 keine statusbilds angeben sein. Weitere Informationen zu Overlay gespeichert und die Status-Images finden Sie unter [Strukturansicht-Steuerelement Bilderlisten](../mfc/tree-control-image-lists.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
