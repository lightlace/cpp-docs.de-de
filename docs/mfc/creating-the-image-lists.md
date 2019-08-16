---
title: Erstellen der Bildliste
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 6687b62b70103894d957a21019008e8781385feb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508785"
---
# <a name="creating-the-image-lists"></a>Erstellen der Bildliste

Das Erstellen von Image Listen ist identisch, unabhängig davon, ob Sie [CListView](../mfc/reference/clistview-class.md) oder [CListCtrl](../mfc/reference/clistctrl-class.md)verwenden.

> [!NOTE]
>  Sie benötigen nur Bildlisten, wenn das Listen Steuerelement `LVS_ICON` den Stil enthält.

Verwenden Sie `CImageList` die-Klasse, um eine oder mehrere Bildlisten zu erstellen (für Symbole in voller Größe, kleine Symbole und Zustände). Weitere Informationen finden Sie unter [CImageList](../mfc/reference/cimagelist-class.md)und [Bildlisten](/windows/win32/Controls/using-list-view-controls) der Listenansicht im Windows SDK.

[CListCtrl:: SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) für jede Bildliste abrufen übergeben Sie einen Zeiger auf das `CImageList` entsprechende-Objekt.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
