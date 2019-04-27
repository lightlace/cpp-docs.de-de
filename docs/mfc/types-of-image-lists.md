---
title: Bildlistenarten
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
ms.openlocfilehash: 939aad78b7cf8cca9c940bae11892d23dbb659cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180849"
---
# <a name="types-of-image-lists"></a>Bildlistenarten

Es gibt zwei Arten von Bildlisten ([CImageList](../mfc/reference/cimagelist-class.md)): nicht maskierte und maskierte. Eine "nicht maskierte Bildliste" besteht aus einer Farbe-Bitmap, die ein oder mehrere Abbilder enthält. Eine "maskierte Bildliste" besteht aus zwei Bitmaps gleicher Größe. Die erste ist eine Farbbitmap, die die Bilder enthält, und die zweite ist eine monochrome Bitmap, die eine Reihe von Masken enthält – eine für jedes Bild in der ersten Bitmap.

Eine der Überladungen der `Create` Member-Funktion akzeptiert ein Flag, um anzugeben, und zwar unabhängig davon, ob die Bildliste maskiert wird. (Alle anderen Überladungen erstellen maskierte Bildlisten.)

Wenn ein nicht maskierte Bild gezeichnet wird, wird er einfach in den Ziel-Gerätekontext kopiert werden; Es ist, also über die vorhandenen Hintergrundfarbe des Gerätekontexts gezeichnet. Wenn ein maskiertes Bild gezeichnet wird, werden die Bits des Bilds mit den Bits der Maske transparente Bereiche in der Bitmap in der Regel erstellen, in dem die Hintergrundfarbe des Zielgerätekontexts durchscheint, kombiniert. Sie können mehrere zeichnungsarten angeben, ein maskiertes Bild zu zeichnen. Beispielsweise können Sie angeben, dass das Bild blinkt, um ein ausgewähltes Objekt anzuzeigen.

## <a name="see-also"></a>Siehe auch

[Verwenden von CImageList](../mfc/using-cimagelist.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
