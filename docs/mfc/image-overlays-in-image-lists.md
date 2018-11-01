---
title: Overlaymasken in Bildlisten
ms.date: 11/04/2016
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
ms.openlocfilehash: dc5c28a38d3024f3d8cbd1fa8b9fe9c1c8a09f93
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603098"
---
# <a name="image-overlays-in-image-lists"></a>Overlaymasken in Bildlisten

Jede Bildliste ([CImageList](../mfc/reference/cimagelist-class.md)) enthält eine Liste der Images, die als Overlaymasken verwendet. Eine "Overlaymaske" ist ein Bild transparent über ein anderes Bild gezeichnet wird. Jedes Image kann als eine Overlaymaske verwendet werden. Sie können bis zu vier Overlaymasken pro Bildliste angeben.

Sie den Index eines Bildes zur Liste der Overlaymasken hinzufügen, mit der [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) Member-Funktion, den Index eines Bildes und der Index des eine Overlaymaske. Beachten Sie, dass die Indizes für die Overlaymasken einsbasierte nullbasiert, sondern sind.

Sie zeichnen eine Overlaymaske, über ein Abbild mit einem einzigen Aufruf `Draw`. Die Parameter enthalten den Index des zu zeichnenden Bildes und der Index ein Overlay-Maske. Verwenden Sie die [INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) Makro, um den Index der Überlagerung Maske angeben. Sie können auch ein Overlay-Image angeben, beim Aufrufen der [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect) Member-Funktion.

## <a name="see-also"></a>Siehe auch

[Verwenden von CImageList](../mfc/using-cimagelist.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

