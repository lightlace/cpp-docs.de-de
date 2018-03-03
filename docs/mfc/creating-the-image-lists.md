---
title: Erstellen der Bildliste | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfb42dc2c14b5092aeb667ea22008abe4d581a6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-image-lists"></a>Erstellen der Bildliste
Erstellen von Bildlisten identisch ist, sowohl bei Verwendung [CListView](../mfc/reference/clistview-class.md) oder [CListCtrl](../mfc/reference/clistctrl-class.md).  
  
> [!NOTE]
>  Sie nur müssen Bildlisten Strukturelement-Steuerelement enthält die `LVS_ICON` Stil.  
  
 Verwenden Sie die Klasse `CImageList` eine oder mehrere Bildlisten (für große Symbole, kleine Symbole und Zustände) zu erstellen. Finden Sie unter [CImageList](../mfc/reference/cimagelist-class.md), und finden Sie unter [Liste Ansicht Bilderlisten](http://msdn.microsoft.com/library/windows/desktop/bb774736) im Windows SDK.  
  
 Rufen Sie [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) für jede Liste image; übergeben Sie einen Zeiger auf die entsprechenden `CImageList` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

