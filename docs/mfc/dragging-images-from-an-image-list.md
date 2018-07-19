---
title: Herausziehen von Bildern aus einer Bildliste | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], dragging images from
- dragging images from image lists [MFC]
- image lists [MFC], dragging images from
- images [MFC], dragging from image lists
ms.assetid: af691db8-e4f0-4046-b7b9-9acc68d3713d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d54984cdc1dc7897fb4f5d1d9680c6a2b95a787d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347164"
---
# <a name="dragging-images-from-an-image-list"></a>Herausziehen von Bildern aus einer Bildliste
[CImageList](../mfc/reference/cimagelist-class.md) beinhaltet Funktionen für ein Bild auf dem Bildschirm ziehen. Die Funktionen zum Ziehen Verschieben eines Bildes reibungslos, Farbe und ohne Blinken des Cursors. Maskierte und Aufheben der Maskierung Bilder können gezogen werden.  
  
 Die [BeginDrag](../mfc/reference/cimagelist-class.md#begindrag) Memberfunktion beginnt einen Drag-Vorgang. Die Parameter umfassen den Index des Abbilds ziehen und den Speicherort des Hotspots innerhalb des Bilds. Der Hotspot ist ein einzelnes Pixel, das die Funktionen zum Ziehen als genaue Bildschirmposition des Bilds erkannt. In der Regel festgelegt eine Anwendung den Hotspot so, dass es mit den Hotspot des Mauszeigers Zeitangabe. Die [Memberfunktion DragMove](../mfc/reference/cimagelist-class.md#dragmove) Memberfunktion wird das Bild an einem neuen Speicherort verschoben.  
  
 Die [DragEnter](../mfc/reference/cimagelist-class.md#dragenter) Memberfunktion legt die ursprüngliche Position des Bilds ziehen Sie in einem Fenster und zeichnet das Bild an der Position. Die Parameter umfassen einen Zeiger auf das Fenster in der das Abbild und einen Punkt, der angibt, die Koordinaten der Position des ersten innerhalb des Fensters gezeichnet werden soll. Die Koordinaten sind relativ zur oberen linken Fensterecke, nicht den Clientbereich. Dasselbe gilt für alle Image-ziehen-Funktionen, die Koordinaten als Parameter verwendet. Dies bedeutet, dass Sie beim Angeben der Koordinaten für die Breite der Elemente des Fensters, z. B. die Rahmen, die Titelleiste und die Menüleiste ausgleichen müssen. Bei Angabe einer **NULL** Fensterhandle beim Aufrufen von `DragEnter`, das die Funktionen zum Ziehen zeichnen das Bild in den Gerätekontext, der die Desktopfenster zugeordnet und die Koordinaten sind relativ zu der oberen linken Ecke des Bildschirms.  
  
 `DragEnter` Sperren alle anderen Updates, die auf das angegebene Fenster, während des Ziehvorgangs. Wenn Sie während eines Ziehvorgangs, z. B. das Ziel eines Drag-and-Drop-Vorgangs, Hervorhebung Zeichnung durchführen müssen können Sie das gezogene Bild vorübergehend ausblenden, indem die [DragLeave](../mfc/reference/cimagelist-class.md#dragleave) Memberfunktion. Sie können auch die [DragShowNoLock](../mfc/reference/cimagelist-class.md#dragshownolock) Memberfunktion.  
  
 Rufen Sie [EndDrag](../mfc/reference/cimagelist-class.md#enddrag) Wenn Sie fertig sind ziehen das Bild.  
  
 Die [SetDragCursorImage](../mfc/reference/cimagelist-class.md#setdragcursorimage) Memberfunktion erstellt ein neues Drag-Image durch Kombinieren von der angegebenen Bilds (in der Regel ein Bild eines Mauscursors) mit dem aktuellen Drag-Image. Da die Funktionen zum Ziehen das neue Image während eines Ziehvorgangs verwenden, sollten Sie verwenden Windows [ShowCursor](http://msdn.microsoft.com/library/windows/desktop/ms648396) Funktion, um den tatsächlichen Cursor nach dem Aufruf ausblenden `SetDragCursorImage`. Andernfalls kann das System angezeigt, haben Sie zwei Mauscursor für die Dauer des Ziehvorgangs.  
  
 Wenn eine Anwendung ruft `BeginDrag`, vom System erstellt eine temporäre interne Bildliste und kopiert das angegebene Bild in der internen Liste ziehen. Sie können einen Zeiger auf die Bildliste temporäre ziehen Sie abrufen, indem Sie mit der [Memberfunktion GetDragImage](../mfc/reference/cimagelist-class.md#getdragimage) Memberfunktion. Die Funktion ruft auch ab, der aktuellen Position von Drag und den Offset des Bilds ziehen Sie relativ zur Ziehposition.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

