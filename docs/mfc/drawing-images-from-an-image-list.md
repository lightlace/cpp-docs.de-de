---
title: Darstellen von Bildern aus einer Bildliste
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], drawing images from
- drawing [MFC], images from image lists
- image lists [MFC], drawing images from
- images [MFC], drawing
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
ms.openlocfilehash: e2058c727620c9aae4ccd9a3fbeaae02c78ce8c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262800"
---
# <a name="drawing-images-from-an-image-list"></a>Darstellen von Bildern aus einer Bildliste

Um ein Bild zu zeichnen, verwenden die [Memberfunktion CImageList:: Draw](../mfc/reference/cimagelist-class.md#draw) Member-Funktion. Geben Sie einen Zeiger auf ein Gerät Context-Objekt, den Index des Bildes, das gezeichnet werden soll, den Speicherort in den Gerätekontext, an dem das Bild gezeichnet werden soll, und einen Satz von Flags an, dass das Zeichnungsformat.

Bei Angabe der **ILD_TRANSPARENT** Stil `Draw` verwendet einen zweistufiger Prozess, ein maskiertes Bild gezeichnet werden soll. Erstens führt eine logische- und -Vorgang für die Bits des Abbilds und die Bits der Maske. Er führt dann eine Logisches XOR-Operation für die Ergebnisse des ersten Vorgangs und die Hintergrundbits des Zielgerätekontexts. Dieser Prozess erstellt transparente Bereiche, in das resultierende Image. bewirkt, dass jeder weiß Bit in der Maske das entsprechende Bit in das resultierende Image transparent sein.

Bevor Sie ein maskiertes Bild wird auf einen einfarbigen Hintergrund zeichnen, verwenden Sie die [SetBkColor](../mfc/reference/cimagelist-class.md#setbkcolor) Memberfunktion versucht, die die Hintergrundfarbe der Liste der Bilder auf die gleiche Farbe als Ziel festzulegen. Festlegen der Textfarbe entfällt die Notwendigkeit, transparente Bereiche in der Abbildung zu erstellen, und ermöglicht `Draw` , das Abbild auf den Ziel-Gerätekontext, was zu einer erheblichen Zunahme der Leistung zu kopieren. Geben Sie zum Zeichnen des Bilds, das **ILD_NORMAL** Format zuzuweisen, wenn Sie aufrufen `Draw`.

Sie können die Hintergrundfarbe für eine maskierte Bildliste festlegen ([CImageList](../mfc/reference/cimagelist-class.md)) zu einem beliebigen Zeitpunkt so, dass die It ordnungsgemäß auf alle Volltonfarbe für den Hintergrund zeichnet. Festlegen der Farbe des Hintergrunds auf **CLR_NONE führt dazu** bewirkt, dass Images, standardmäßig transparent gezeichnet werden soll. Verwenden Sie zum Abrufen der Farbe des Hintergrunds einer Bildliste der [GetBkColor](../mfc/reference/cimagelist-class.md#getbkcolor) Member-Funktion.

Die **ILD_BLEND25** und **ILD_BLEND50** Stile mischen, das Image mit der Hervorhebungsfarbe des Systems. Diese Formate sind nützlich, wenn Sie ein maskiertes Image verwenden, um ein Objekt darzustellen, die der Benutzer auswählen kann. Beispielsweise können Sie die **ILD_BLEND50** Stil zum Zeichnen des Bilds, wenn der Benutzer sie auswählt.

Ein nicht maskierte Image wird kopiert, auf das Ziel Gerät Kontext die `SRCCOPY` rastervorgang. Die Farben in der Abbildung werden unabhängig von die Hintergrundfarbe des Gerätekontexts angezeigt. Die zeichnungsarten in angegebenen `Draw` auch haben keine Auswirkungen auf die Darstellung eines nicht maskierte Images.

Zusätzlich zu den Draw-Memberfunktion, eine andere Funktion [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect), erweitert die Möglichkeit, ein Bild zu rendern. `DrawIndirect` erfordert, als Parameter ein [IMAGELISTDRAWPARAMS](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams) Struktur. Diese Struktur kann verwendet werden, um das Rendering des aktuellen Bilds, einschließlich der Verwendung von rastervorgangscode (ROP) anpassen. Weitere Informationen zu ROP-Codes finden Sie unter [Rastervorgangscode](/windows/desktop/gdi/raster-operation-codes) und [Bitmaps als Pinsel](/windows/desktop/gdi/bitmaps-as-brushes) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CImageList](../mfc/using-cimagelist.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
