---
title: Erstellen der Bildliste | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4878caa735562a76bc4afe64b7d5bb1ecb22e069
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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

