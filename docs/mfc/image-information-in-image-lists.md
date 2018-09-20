---
title: Imageinformationen in Bildlisten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c98bc629cde74cf7a6fc8a416de862f50a1dd5ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422284"
---
# <a name="image-information-in-image-lists"></a>Bildinformationen in Bildlisten

[CImageList](../mfc/reference/cimagelist-class.md) umfasst eine Reihe von Funktionen, die für das Abrufen von Informationen aus einer Bildliste. Die [GetImageInfo](../mfc/reference/cimagelist-class.md#getimageinfo) Member-Funktion füllt eine `IMAGEINFO` -Struktur mit Informationen über ein einzelnes Bild, einschließlich der Handles, die Bitmaps für Bild und die Maske, die Anzahl von Farbebenen und Bits pro Pixel und das umgebende Rechteck des Bilds in der Image-Bitmap. Sie können diese Informationen verwenden, die Bitmaps für das Image direkt zu bearbeiten.

Die [GetImageCount](../mfc/reference/cimagelist-class.md#getimagecount) Member-Funktion ruft die Anzahl der Bilder in einer Bildliste ab.

Sie können ein Symbol, das basierend auf einem Bild und der Maske in einer Bildliste verwenden erstellen die [ExtractIcon](../mfc/reference/cimagelist-class.md#extracticon) Member-Funktion. Die Funktion gibt das Handle des neuen Symbols.

## <a name="see-also"></a>Siehe auch

[Verwenden von CImageList](../mfc/using-cimagelist.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

