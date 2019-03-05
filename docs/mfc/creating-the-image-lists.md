---
title: Erstellen der Bildliste
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 844bfe71f7b03f299f57b0fd4558b7e9eacf67c2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265781"
---
# <a name="creating-the-image-lists"></a>Erstellen der Bildliste

Erstellen von Bildlisten identisch ist, unabhängig davon, ob Sie [CListView](../mfc/reference/clistview-class.md) oder [CListCtrl](../mfc/reference/clistctrl-class.md).

> [!NOTE]
>  Sie nur müssen image aufgelistet, wenn das Listensteuerelement enthält die `LVS_ICON` Stil.

Verwenden Sie Klasse `CImageList` erstellen Sie eine oder mehrere Bildlisten (für in voller Größe Symbole, kleine Symbole und Zustände). Finden Sie unter [CImageList](../mfc/reference/cimagelist-class.md), und finden Sie unter [List View Image Lists](/windows/desktop/Controls/using-list-view-controls) im Windows SDK.

Rufen Sie [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) für jede Liste image, übergeben Sie einen Zeiger auf die entsprechenden `CImageList` Objekt.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
