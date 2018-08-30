---
title: Erstellen der Bildliste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53cf33a551dc95e7ed282b599673f627ff8a7b21
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220936"
---
# <a name="creating-the-image-lists"></a>Erstellen der Bildliste
Erstellen von Bildlisten identisch ist, unabhängig davon, ob Sie [CListView](../mfc/reference/clistview-class.md) oder [CListCtrl](../mfc/reference/clistctrl-class.md).  
  
> [!NOTE]
>  Sie nur müssen image aufgelistet, wenn das Listensteuerelement enthält die `LVS_ICON` Stil.  
  
 Verwenden Sie Klasse `CImageList` erstellen Sie eine oder mehrere Bildlisten (für in voller Größe Symbole, kleine Symbole und Zustände). Finden Sie unter [CImageList](../mfc/reference/cimagelist-class.md), und finden Sie unter [List View Image Lists](/windows/desktop/Controls/using-list-view-controls) im Windows SDK.  
  
 Rufen Sie [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) für jede Liste image, übergeben Sie einen Zeiger auf die entsprechenden `CImageList` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

