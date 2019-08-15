---
title: Übersicht über Elementzustände des Struktursteuerung-Steuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- states, CTreeCtrl items
- tree controls [MFC], item states overview
- CTreeCtrl class [MFC], item states
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
ms.openlocfilehash: bbeabf69f174fcf172808ff71f07ed05f1dc9675
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511043"
---
# <a name="tree-control-item-states-overview"></a>Übersicht über Elementzustände des Struktursteuerung-Steuerelements

Jedes Element in einem Struktur Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) hat einen aktuellen Zustand. Ein Element kann z. b. ausgewählt, deaktiviert, erweitert und so weiter. Zum größten Teil legt das Struktur Steuerelement den Zustand eines Elements automatisch so fest, dass Benutzeraktionen wie z. b. die Auswahl eines Elements angezeigt werden. Sie können jedoch auch den Zustand eines Elements festlegen, indem Sie die [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate) -Member-Funktion verwenden und den aktuellen Zustand eines Elements mithilfe der [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate) -Member-Funktion abrufen. Eine umfassende Liste der Element Zustände finden Sie Unterstruktur [Ansicht-Steuerelement Konstanten](/windows/win32/Controls/tree-view-control-item-states) in der Windows SDK.

Der aktuelle Zustand eines Elements wird durch den *nState* -Parameter angegeben. Mit einem Struktur Steuerelement kann der Zustand eines Elements geändert werden, um eine Benutzeraktion widerzuspiegeln, z. b. das Auswählen des Elements oder das Festlegen des Fokus auf das Element. Außerdem kann eine Anwendung den Zustand eines Elements ändern, um das Element zu deaktivieren oder auszublenden oder ein Überlagerungs Bild oder ein Zustands Bild anzugeben.

Wenn Sie den Zustand eines Elements angeben oder ändern, gibt der *nStateMask* -Parameter an, welche Zustands Bits festgelegt werden sollen, und der *nState* -Parameter enthält die neuen Werte für diese Bits. Im folgenden Beispiel wird z. b. der aktuelle Zustand eines übergeordneten Elements (angegeben durch *hparameentitem*) in `CTreeCtrl` einem-`m_treeCtrl` `TVIS_EXPANDPARTIAL`Objekt () in geändert:

[!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]

Ein weiteres Beispiel für das Ändern des Zustands besteht darin, das Überlagerungs Bild eines Elements festzulegen. Um dies zu erreichen, muss *nStateMask* den `TVIS_OVERLAYMASK` Wert enthalten, und *nState* muss den 1-basierten Index des Überlagerungs Bilds enthalten, das mithilfe des [INDEXTOOVERLAYMASK](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask) -Makros nach links verschoben wurde. Der Index kann 0 sein, um kein Überlagerungs Bild anzugeben. Das Überlagerungs Bild muss der Liste der Überlagerungs Bilder des Struktur Steuer Elements durch einen vorherigen-aufrufsbefehl der [CImageList::](../mfc/reference/cimagelist-class.md#setoverlayimage) absetimage-Funktion hinzugefügt worden sein. Die-Funktion gibt den 1-basierten Index des hinzu zufügenden Bilds an. Dies ist der Index, der mit dem indexyoverlaymask-Makro verwendet wird. Ein Struktur Steuerelement kann bis zu vier Überlagerungs Bilder aufweisen.

Um das Zustands Bild eines Elements festzulegen, muss *nStateMask* den `TVIS_STATEIMAGEMASK` Wert enthalten, und *nState* muss den 1-basierten Index des Zustands Bilds mit dem [indextostateimagemask](/windows/win32/api/commctrl/nf-commctrl-indextostateimagemask) -Makro in die linken 12 Bits verschieben. Der Index kann 0 sein, um kein Status Bild anzugeben. Weitere Informationen zu Überlagerungs-und Zustands Bildern finden Sie Unterstruktur Steuerelement- [Bildlisten](../mfc/tree-control-image-lists.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
