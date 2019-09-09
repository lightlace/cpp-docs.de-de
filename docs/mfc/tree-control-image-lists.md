---
title: Bilderliste für das Struktursteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- images [MFC], lists in tree controls
- tree controls [MFC], image lists
- CTreeCtrl class [MFC], image lists
ms.assetid: f560c4f2-20d2-4d28-ac33-4017e65fb0a6
ms.openlocfilehash: 8f9e323244657ea6a7cc132deab6deedfcd1a167
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513371"
---
# <a name="tree-control-image-lists"></a>Bilderliste für das Struktursteuerelement

Jedem Element in einem Struktur Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) kann ein paar von bitzugeordneten Bildern zugeordnet werden. Die Bilder werden auf der linken Seite der Bezeichnung eines Elements angezeigt. Ein Bild wird angezeigt, wenn das Element ausgewählt wird, und das andere wird angezeigt, wenn das Element nicht ausgewählt ist. Ein Element kann z. b. einen geöffneten Ordner anzeigen, wenn er ausgewählt wird, und einen geschlossenen Ordner, wenn er nicht ausgewählt ist.

Wenn Sie Element Bilder verwenden möchten, müssen Sie eine Bildliste erstellen, indem Sie ein [CImageList](../mfc/reference/cimagelist-class.md) -Objekt erstellen und mithilfe der Funktion [CImageList:: Create](../mfc/reference/cimagelist-class.md#create) die zugeordnete Bildliste erstellen. Fügen Sie dann der Liste die gewünschten Bitmaps hinzu, und ordnen Sie die Liste mit der [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist) -Member-Funktion dem Struktur Steuerelement zu. Standardmäßig wird für alle Elemente das erste Bild in der Bildliste für die ausgewählten und nicht ausgewählten Zustände angezeigt. Sie können das Standardverhalten für ein bestimmtes Element ändern, indem Sie die Indizes der ausgewählten und nicht ausgewählten Images angeben, wenn Sie das Element mithilfe der [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) -Member-Funktion dem Struktur Steuerelement hinzufügen. Sie können die Indizes nach dem Hinzufügen eines Elements [mithilfe der Member](../mfc/reference/ctreectrl-class.md#setitemimage) -Funktion "Member" von "Member" ändern.

Die Bildlisten eines Struktur Steuer Elements können auch Überlagerungs Bilder enthalten, die für die Überlagerung von Element Bildern entwickelt wurden. Ein Wert ungleich 0 (null) in Bits 8 bis 11 des Zustands eines Baum Steuerungs Elements gibt den 1-basierten Index eines Überlagerungs Bilds an (0 gibt kein Überlagerungs Bild an). Da ein 4-Bit-, ein-basierter Index verwendet wird, müssen Überlagerungs Bilder in den ersten 15 Bildern der Bildlisten aufgeführt werden. Weitere Informationen zu Struktur Steuerungselement Zuständen finden Sie Unterstruktur [Steuerungselement Zustände (Übersicht](../mfc/tree-control-item-states-overview.md) ) weiter oben in diesem Thema.

Wenn eine Status Bild Liste angegeben ist, reserviert ein Struktur Steuerelement für ein Zustands Bild links neben dem Symbol des einzelnen Elements Platz. Eine Anwendung kann Zustands Bilder, wie z. b. aktivierte und gelöschte Kontrollkästchen, zum Angeben von Anwendungs definierten Element Zuständen verwenden. Ein Wert ungleich 0 (null) in Bits 12 bis 15 gibt den 1-basierten Index eines Status Bilds an (0 gibt an, dass kein Status Bild angezeigt wird).

Wenn Sie anstelle des Index eines Bilds den **I_IMAGECALLBACK** -Wert angeben, können Sie das ausgewählte oder nicht ausgewählte Bild verzögern, bis das Element neu gezeichnet wird. **I_IMAGECALLBACK** weist das Struktur Steuerelement an, die Anwendung für den Index abzufragen, indem die [TVN_GETDISPINFO](/windows/win32/Controls/tvn-getdispinfo) -Benachrichtigungs Meldung gesendet wird.

Die [GetImageList](../mfc/reference/ctreectrl-class.md#getimagelist) -Member-Funktion Ruft das Handle der Bildliste eines Struktur Steuer Elements ab. Diese Funktion ist nützlich, wenn Sie der Liste weitere Bilder hinzufügen müssen. Weitere Informationen zu Bildlisten finden Sie unter [Verwenden von CImageList](../mfc/using-cimagelist.md), [CImageList](../mfc/reference/cimagelist-class.md) in der *MFC-Referenz*und [Bildlisten](/windows/win32/controls/image-lists) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
