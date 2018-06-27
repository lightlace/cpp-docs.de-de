---
title: Bildlistenarten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 580969195de9241d935e1c27e1659f6e0c4c40ab
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953207"
---
# <a name="types-of-image-lists"></a>Bildlistenarten
Es gibt zwei Arten von Bildlisten ([CImageList](../mfc/reference/cimagelist-class.md)): nicht maskierte und maskierte. Eine "nicht maskierte Bildliste" besteht aus einer Farbbitmap, die ein oder mehrere Abbilder enthält. Eine "maskierte Bildliste" besteht aus zwei Bitmaps gleicher Größe. Die erste ist eine Farbbitmap, die die Bilder enthält, und die zweite ist eine monochrome Bitmap, die eine Reihe von Masken enthält – eine für jedes Bild in der ersten Bitmap.  
  
 Eine der Überladungen der der `Create` Member-Funktion akzeptiert ein Flag zur Angabe, und zwar unabhängig davon, ob die Bildliste maskiert wird. (Andere Überladungen erstellen maskierten Bildlisten.)  
  
 Wenn ein nicht maskierten Bild gezeichnet wird, wird es einfach in den Ziel-Gerätekontext kopiert; Es wird also über die vorhandenen Hintergrundfarbe des Gerätekontexts gezeichnet. Wenn ein maskiertes Bild gezeichnet wird, werden die Bits des Bilds mit den Bit der Maske, erzeugt in der Regel transparente Bereiche in der Bitmap, in dem die Hintergrundfarbe des Zielgerätekontexts durchscheint, kombiniert. Sie können mehrere zeichnungsarten beim Zeichnen eines maskierten Bildes angeben. Beispielsweise können Sie angeben, dass das Bild blinkt, um ein ausgewähltes Objekt anzugeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

