---
title: Bilderliste für das Struktursteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- images [MFC], lists in tree controls
- tree controls [MFC], image lists
- CTreeCtrl class [MFC], image lists
ms.assetid: f560c4f2-20d2-4d28-ac33-4017e65fb0a6
ms.openlocfilehash: 2b680ece131df434b65f02501f78f0cdb6507f08
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551761"
---
# <a name="tree-control-image-lists"></a>Bilderliste für das Struktursteuerelement

Jedes Element in einem Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) kann ein Paar von Bitmapbildern zugeordnet haben. Die Bilder werden auf der linken Seite der die Bezeichnung eines Elements angezeigt. Ein Bild wird angezeigt, wenn das Element ist ausgewählt, und der andere wird angezeigt, wenn das Element nicht ausgewählt ist. Beispielsweise kann ein Element anzuzeigen einen geöffneten Ordner, wenn diese Option ausgewählt ist und einen geschlossenen Ordner, wenn es nicht aktiviert ist.

Zum Elementbilder verwenden zu können, müssen Sie eine Bildliste erstellen, durch das Erstellen einer [CImageList](../mfc/reference/cimagelist-class.md) -Objekt, und Verwenden der [CImageList:: Create](../mfc/reference/cimagelist-class.md#create) Funktion, um die zugeordnete Bildliste zu erstellen. Klicken Sie dann die gewünschte Bitmaps zur Liste hinzufügen, und ordnen Sie die Liste das Strukturansicht-Steuerelement, indem die [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist) Member-Funktion. Standardmäßig zeigen alle Elemente das erste Bild in der Bildliste für die ausgewählte und nicht ausgewählten Status. Sie können das Standardverhalten für ein bestimmtes Element ändern, indem Sie die Indizes der ausgewählten und nicht ausgewählten Bilder angeben, beim Hinzufügen des Elements, das Strukturansicht-Steuerelement mithilfe der [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) Member-Funktion. Sie können die Indizes nach dem Hinzufügen eines Elements mit Ändern der [Memberfunktion SetItemImage](../mfc/reference/ctreectrl-class.md#setitemimage) Member-Funktion.

Bilderliste für das ein Strukturansicht-Steuerelement können auch Overlay-Images enthalten, die entwickelt wurden, um auf Elementbilder angezeigt werden. Ein Wert ungleich NULL in Zustandsbits, 8 bis 11 ein Strukturansicht-Steuerelement-Element gibt den einsbasierten Index eines Overlaybildes an (0 bedeutet kein Overlay-Image). Da ein 4-Bit-, 1 basierenden Index verwendet wird, muss die Overlay-Images für die ersten 15 Bilder in der Bildliste. Weitere Informationen über Elementzustände des struktursteuerung-Steuerelements finden Sie unter [Strukturansicht-Steuerelement Übersicht über Elementzustände](../mfc/tree-control-item-states-overview.md) weiter oben in diesem Thema.

Wenn eine Bildliste Status angegeben wird, reserviert ein Strukturansicht-Steuerelement Speicherplatz auf der linken Seite jedes Elements Symbol für die Image-Zustand. Eine Anwendung kann Zustandsgrafiken, z. B. Kontrollkästchen aktiviert und deaktiviert, an der Anwendung definierte Element-Zustände verwenden. Ein Wert ungleich NULL in Bits 12 bis 15 gibt den einsbasierten Index eines Zustandsbildes (0 bedeutet kein Zustandsbild).

Durch Angabe der **I_IMAGECALLBACK** Wert anstatt den Index eines Bildes kann verzögert werden ausgewählte oder nicht ausgewählten Bild angeben, bis das Element ist zu neu gezeichnet wird. **I_IMAGECALLBACK** leitet das Strukturansicht-Steuerelement, um die Anwendung für den Index senden abzufragen der [TVN_GETDISPINFO](/windows/desktop/Controls/tvn-getdispinfo) Benachrichtigung.

Die [Memberfunktion GetImageList](../mfc/reference/ctreectrl-class.md#getimagelist) Memberfunktion Ruft das Handle der Bildliste ein Strukturansicht-Steuerelement ab. Diese Funktion ist nützlich, wenn die Liste weitere Bilder hinzugefügt werden sollen. Weitere Informationen zu Bildlisten, finden Sie unter [Verwenden von CImageList](../mfc/using-cimagelist.md), [CImageList](../mfc/reference/cimagelist-class.md) in die *MFC-Referenz*, und [Bilderlisten](https://msdn.microsoft.com/library/windows/desktop/bb761389) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

