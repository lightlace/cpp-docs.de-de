---
title: Drag &amp; Drop-Operationen für das Struktursteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
ms.openlocfilehash: 5d2c5aa511844a3d7cbe64d9a15f8ffb46046b29
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510905"
---
# <a name="tree-control-drag-and-drop-operations"></a>Drag &amp; Drop-Operationen für das Struktursteuerelement

Ein Struktur Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) sendet eine Benachrichtigung, wenn der Benutzer mit dem Ziehen eines Elements beginnt. Das-Steuerelement sendet eine [TVN_BEGINDRAG](/windows/win32/Controls/tvn-begindrag) -Benachrichtigungs Meldung, wenn der Benutzer mit dem Ziehen eines Elements mit der linken Maustaste beginnt und eine [TVN_BEGINRDRAG](/windows/win32/Controls/tvn-beginrdrag) -Benachrichtigungs Meldung angezeigt wird, wenn der Benutzer mit der rechten Maustaste loslässt. Sie können verhindern, dass ein Struktur Steuerelement diese Benachrichtigungen sendet, indem Sie dem Struktur Steuerelement den TVS_DISABLEDRAGDROP-Stil erteilen.

Sie erhalten ein Bild, das während eines Zieh Vorgangs angezeigt wird, indem Sie die [CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage) -Member-Funktion aufrufen. Das Struktur Steuerelement erstellt eine Zieh Bitmap auf der Grundlage der Bezeichnung des gezogenen Elements. Dann erstellt das Struktur Steuerelement eine Bildliste, fügt es der Bitmap hinzu und gibt einen Zeiger auf das [CImageList](../mfc/reference/cimagelist-class.md) -Objekt zurück.

Sie müssen den Code bereitstellen, der das Element tatsächlich zieht. Dies umfasst in der Regel die Verwendung der Zieh Funktionen der Abbild Listen Funktionen und die Verarbeitung der [WM_MOUSEMOVE](/windows/win32/inputdev/wm-mousemove) -und [WM_LBUTTONUP](/windows/win32/inputdev/wm-lbuttonup) (oder [WM_RBUTTONUP](/windows/win32/inputdev/wm-rbuttonup))-Nachrichten, die nach dem Beginn des Zieh Vorgangs gesendet werden. Weitere Informationen zu den Funktionen der Bildliste finden Sie unter [CImageList](../mfc/reference/cimagelist-class.md) in den *MFC-Referenz* -und [Bildlisten](/windows/win32/controls/image-lists) in der Windows SDK. Weitere Informationen zum Ziehen eines Struktur Steuerelement Elements finden Sie unter [Ziehen des Struktur Ansichts Elements](/windows/win32/Controls/tree-view-controls), auch im Windows SDK.

Wenn Elemente in einem Struktur Steuerelement die Ziele eines Drag & Drop-Vorgangs sind, müssen Sie wissen, wenn sich der Mauszeiger auf einem Ziel Element befindet. Sie können herausfinden, indem Sie die Funktion " [HitTest](../mfc/reference/ctreectrl-class.md#hittest) Member" aufrufen. Sie geben entweder einen Punkt und eine ganze Zahl oder die Adresse einer [TVHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-tvhittestinfo) -Struktur an, die die aktuellen Koordinaten des Mauszeigers enthält. Wenn die Funktion zurückgibt, enthält die ganze Zahl oder Struktur ein Flag, das die Position des Mauszeigers relativ zum Struktur Steuerelement angibt. Wenn sich der Cursor über einem Element im Struktur Steuerelement befindet, enthält die Struktur auch das Handle des Elements.

Sie können angeben, dass ein Element das Ziel eines Drag & Drop-Vorgangs ist, indem Sie die Member-Funktion von [SetItem](../mfc/reference/ctreectrl-class.md#setitem) aufrufen, um den `TVIS_DROPHILITED` Status auf den Wert festzulegen. Ein Element mit diesem Zustand wird in dem Format gezeichnet, mit dem ein Drag & Drop-Ziel angegeben wird.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
