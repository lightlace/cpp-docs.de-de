---
title: "Bild überlagert in Bildlisten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5e70365040b5f009e634a4867a4a1f974d47bd61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="image-overlays-in-image-lists"></a>Overlaymasken in Bildlisten
Jede Bildliste ([CImageList](../mfc/reference/cimagelist-class.md)) enthält eine Liste von Bildern für die Verwendung als Overlaymasken. Eine Overlaymaske"" ist ein Bild transparent über ein anderes Bild gezeichnet. Bilder kann als eine Overlaymaske verwendet werden. Sie können bis zu vier Overlaymasken pro Bildliste angeben.  
  
 Den Index eines Bilds wird zur Liste der Overlaymasken hinzufügen, mit der [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) Memberfunktion, den Index eines Bilds und den Index des eine Overlaymaske. Beachten Sie, dass die Indizes für die Overlaymasken einsbasierte anstatt nullbasiert sind.  
  
 Sie zeichnen eine Overlaymaske auf ein Bild mit einem einzigen Aufruf **zeichnen**. Die Parameter umfassen den Index des zu zeichnenden Bilds und den Index ein Overlay-Maske. Verwenden Sie die [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) Makro, das den Index der Overlaymaske angeben. Sie können auch ein Overlaybild angeben, beim Aufrufen der [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

