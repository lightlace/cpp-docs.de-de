---
title: Darstellen von Bildern aus einer Bildliste
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], drawing images from
- drawing [MFC], images from image lists
- image lists [MFC], drawing images from
- images [MFC], drawing
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
ms.openlocfilehash: fb307d5557c0e136c1c44c29f08af6062bb1c19d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508611"
---
# <a name="drawing-images-from-an-image-list"></a>Darstellen von Bildern aus einer Bildliste

Um ein Bild zu zeichnen, verwenden Sie die Funktion [CImageList::D RAW](../mfc/reference/cimagelist-class.md#draw) Member. Sie geben einen Zeiger auf ein Gerätekontext Objekt, den Index des zu zeichnenden Bilds, die Position im Gerätekontext, an dem das Bild gezeichnet werden soll, und einen Satz von Flags zum Angeben der Zeichnungs Art an.

Wenn Sie den **ILD_TRANSPARENT** -Stil angeben `Draw` , wird von ein zweistufiger Prozess zum Zeichnen eines maskierten Bilds verwendet. Zuerst führt Sie eine logische and-Operation für die Bits des Bilds und die Bits der Maske aus. Anschließend führt er einen logischen XOR-Vorgang für die Ergebnisse des ersten Vorgangs und die hintergrundbits des Zielgeräte Kontexts aus. Dieser Prozess erstellt transparente Bereiche im resultierenden Image. Das heißt, jedes weiße Bit in der Maske bewirkt, dass das entsprechende Bit im resultierenden Bild transparent ist.

Vor dem Zeichnen eines maskierten Bilds auf einem voll Tonfarben-Hintergrund sollten Sie die Element Funktion [SetBkColor](../mfc/reference/cimagelist-class.md#setbkcolor) verwenden, um die Hintergrundfarbe der Bildliste auf die gleiche Farbe wie das Ziel festzulegen. Durch das Festlegen der Farbe entfällt die Notwendigkeit, transparente Bereiche im Bild zu erstellen `Draw` , und es wird ermöglicht, das Bild einfach in den Zielgeräte Kontext zu kopieren, was zu einer deutlichen Leistungssteigerung führt. Um das Bild zu zeichnen, geben Sie den **ILD_NORMAL** -Stil `Draw`an, wenn Sie aufrufen.

Sie können die Hintergrundfarbe für eine maskierte Bildliste ([CImageList](../mfc/reference/cimagelist-class.md)) jederzeit festlegen, damit Sie auf einem beliebigen Solid-Hintergrund ordnungsgemäß funktioniert. Das Festlegen der Hintergrundfarbe auf **CLR_NONE** bewirkt, dass Bilder standardmäßig transparent gezeichnet werden. Um die Hintergrundfarbe einer Bildliste abzurufen, verwenden Sie die [GetBkColor](../mfc/reference/cimagelist-class.md#getbkcolor) -Member-Funktion.

Die Stile **ILD_BLEND25** und **ILD_BLEND50** weisen das Bild mit der Hervorhebungs Farbe des Systems an. Diese Stile sind nützlich, wenn Sie ein maskiertes Bild verwenden, um ein Objekt darzustellen, das der Benutzer auswählen kann. Beispielsweise können Sie den **ILD_BLEND50** -Stil zum Zeichnen des Bilds verwenden, wenn es vom Benutzer ausgewählt wird.

Ein nicht maskiertes Bild wird mithilfe des `SRCCOPY` Raster Vorgangs in den Zielgeräte Kontext kopiert. Die Farben im Bild erscheinen unabhängig von der Hintergrundfarbe des Geräte Kontexts identisch. Die in `Draw` angegebenen Zeichnungs Stile haben auch keine Auswirkung auf das Aussehen eines nicht maskierten Bilds.

Zusätzlich zur Draw-Member-Funktion erweitert eine andere Funktion, [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect), die Fähigkeit zum Rendering eines Bilds. `DrawIndirect`übernimmt als Parameter eine [imagelistdrawparameams](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams) -Struktur. Diese Struktur kann zum Anpassen des Renderings des aktuellen Bilds verwendet werden, einschließlich der Verwendung von "Raster Operation (ROP)"-Codes. Weitere Informationen zu den Code-Codes finden Sie unter [Raster Vorgangs Codes](/windows/win32/gdi/raster-operation-codes) und [Bitmaps als Pinsel](/windows/win32/gdi/bitmaps-as-brushes) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CImageList](../mfc/using-cimagelist.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
