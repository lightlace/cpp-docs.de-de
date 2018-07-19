---
title: Bild der Informationen in Bildlisten | Microsoft Docs
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
ms.openlocfilehash: 6b45a685a9de44bdc40f83481cb83ef58a5c4234
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343712"
---
# <a name="image-information-in-image-lists"></a>Bildinformationen in Bildlisten
[CImageList](../mfc/reference/cimagelist-class.md) umfasst eine Reihe von Funktionen, die Informationen aus einer Bildliste abrufen. Die [GetImageInfo](../mfc/reference/cimagelist-class.md#getimageinfo) Member-Funktion füllt eine `IMAGEINFO` Struktur mit Informationen über ein einzelnes Bild, einschließlich der Ziehpunkte des Bitmaps Bild und die Maske, die Anzahl von Farbebenen und Bits pro Pixel und das umschließende Rechteck des Bilds in der Image-Bitmap. Diese Informationen können Sie um die Bitmaps für das Bild direkt zu bearbeiten.  
  
 Die [GetImageCount](../mfc/reference/cimagelist-class.md#getimagecount) Memberfunktion Ruft die Anzahl von Bildern in einer Bildliste ab.  
  
 Sie können ein Symbol basierend auf einem Bild und die Maske in einer Bildliste mit Erstellen der [ExtractIcon](../mfc/reference/cimagelist-class.md#extracticon) Memberfunktion. Die Funktion gibt das Handle für das Symbol "Neu".  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

