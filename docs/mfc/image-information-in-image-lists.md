---
title: Bildinformationen in Bildlisten
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
ms.openlocfilehash: 7b83b7e5f7de6f8ccca95d732f71a5d73a97e943
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263064"
---
# <a name="image-information-in-image-lists"></a>Bildinformationen in Bildlisten

[CImageList](../mfc/reference/cimagelist-class.md) umfasst eine Reihe von Funktionen, die für das Abrufen von Informationen aus einer Bildliste. Die [GetImageInfo](../mfc/reference/cimagelist-class.md#getimageinfo) Member-Funktion füllt eine `IMAGEINFO` -Struktur mit Informationen über ein einzelnes Bild, einschließlich der Handles, die Bitmaps für Bild und die Maske, die Anzahl von Farbebenen und Bits pro Pixel und das umgebende Rechteck des Bilds in der Image-Bitmap. Sie können diese Informationen verwenden, die Bitmaps für das Image direkt zu bearbeiten.

Die [GetImageCount](../mfc/reference/cimagelist-class.md#getimagecount) Member-Funktion ruft die Anzahl der Bilder in einer Bildliste ab.

Sie können ein Symbol, das basierend auf einem Bild und der Maske in einer Bildliste verwenden erstellen die [ExtractIcon](../mfc/reference/cimagelist-class.md#extracticon) Member-Funktion. Die Funktion gibt das Handle des neuen Symbols.

## <a name="see-also"></a>Siehe auch

[Verwenden von CImageList](../mfc/using-cimagelist.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
