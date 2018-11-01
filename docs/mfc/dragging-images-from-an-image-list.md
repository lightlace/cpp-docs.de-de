---
title: Herausziehen von Bildern aus einer Bildliste
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], dragging images from
- dragging images from image lists [MFC]
- image lists [MFC], dragging images from
- images [MFC], dragging from image lists
ms.assetid: af691db8-e4f0-4046-b7b9-9acc68d3713d
ms.openlocfilehash: 9d42e9cdd8e2711fc6ed6aa0d08a19b8bc55d5f1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562200"
---
# <a name="dragging-images-from-an-image-list"></a>Herausziehen von Bildern aus einer Bildliste

[CImageList](../mfc/reference/cimagelist-class.md) enthält Funktionen für das ein Bild auf dem Bildschirm ziehen. Die Funktionen zum Ziehen verschieben Sie ein Bild reibungslos, Farbe und ohne Blinken des Cursors. Maskierte und Aufheben der Maskierung Images können gezogen werden.

Die [BeginDrag](../mfc/reference/cimagelist-class.md#begindrag) Memberfunktion beginnt einen Drag-Vorgang. Die Parameter enthalten den Index des Bildes ziehen und den Speicherort des Hotspots im Abbild. Der Hotspot ist ein einzelnes Pixel, das die Funktionen zum Ziehen als genaue Bildschirmposition des Bilds zu erkennen. In der Regel festgelegt eine Anwendung den Hotspot so, dass es mit den Hotspot des Mauszeigers übereinstimmt. Die [Memberfunktion DragMove](../mfc/reference/cimagelist-class.md#dragmove) Member-Funktion wird das Bild an einem neuen Speicherort verschoben.

Die ["DragEnter"](../mfc/reference/cimagelist-class.md#dragenter) Memberfunktion legt die ursprüngliche Position des Bilds ziehen Sie in einem Fenster und zeichnet das Bild an der Position. Die Parameter enthalten einen Zeiger auf das Fenster in der das Abbild und einen Punkt, der angibt, die Koordinaten der die ursprüngliche Position innerhalb des Fensters gezeichnet werden soll. Die Koordinaten sind relativ zur oberen linken Fensterecke, nicht den Clientbereich. Dasselbe gilt für alle das Ziehen von Image-Funktionen, die Koordinaten als Parameter akzeptieren. Dies bedeutet, dass Sie die Breite des Fensterelemente, z. B. die Rahmen, Titelleiste und Menüleiste kompensieren müssen, wenn Sie die Koordinaten angeben. Bei Angabe einer **NULL** Fensterhandle beim Aufrufen von `DragEnter`, die Funktionen zum Ziehen, das Bild im Zusammenhang mit dem Desktopfenster Gerätekontext zeichnen und die Koordinaten sind relativ zu der oberen linken Ecke des Bildschirms.

`DragEnter` Sperrt alle anderen Updates des angegebenen Fensters während des Ziehvorgangs an. Wenn Sie alle Zeichnungen während eines Ziehvorgangs, z. B. markieren das Ziel eines Drag & Drop-Vorgangs müssen, können Sie das gezogene Bild vorübergehend ausblenden, mit der ["DragLeave"](../mfc/reference/cimagelist-class.md#dragleave) Member-Funktion. Sie können auch die [DragShowNoLock](../mfc/reference/cimagelist-class.md#dragshownolock) Member-Funktion.

Rufen Sie [EndDrag](../mfc/reference/cimagelist-class.md#enddrag) Sie anschließend das Bild zu ziehen.

Die [SetDragCursorImage](../mfc/reference/cimagelist-class.md#setdragcursorimage) Member-Funktion erstellt ein neues Drag-Image durch die Kombination der angegebenen Bilds (in der Regel eine Maus Cursorbild) mit dem aktuellen Drag-Image. Da die Funktionen zum Ziehen das neue Image während eines Ziehvorgangs verwenden, befolgen Sie die Windows [ShowCursor](/windows/desktop/api/winuser/nf-winuser-showcursor) Funktion, um den tatsächlichen Cursor nach dem Aufruf ausblenden `SetDragCursorImage`. Andernfalls kann das System angezeigt, damit zwei Mauscursor für die Dauer des Ziehvorgangs.

Wenn eine Anwendung ruft `BeginDrag`, das System erstellt eine temporäre, interne Bildliste und kopiert das angegebene Bild in der internen Liste ziehen. Sie können einen Zeiger auf die Bildliste für die temporäre ziehen Sie abrufen, indem Sie mit der [Memberfunktion GetDragImage](../mfc/reference/cimagelist-class.md#getdragimage) Member-Funktion. Die Funktion ruft auch die aktuelle Position der Drag & und den Offset des Bilds ziehen Sie relativ zur Ziehposition.

## <a name="see-also"></a>Siehe auch

[Verwenden von CImageList](../mfc/using-cimagelist.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

