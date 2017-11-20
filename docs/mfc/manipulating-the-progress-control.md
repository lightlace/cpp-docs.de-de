---
title: Bearbeiten des Statussteuerelements | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CProgressCtrl class [MFC], working with
- progress controls [MFC], manipulating
- CProgressCtrl class [MFC], manipulating
- controlling progress controls [MFC]
- CProgressCtrl class [MFC], using
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c51be1d55958dce6bacd86eacfd134615c4dc0ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="manipulating-the-progress-control"></a>Bearbeiten des Statussteuerelements
Es gibt drei Möglichkeiten zum Ändern der aktuellen Position des ein Statussteuerelement ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)).  
  
-   Die Position kann durch einen vordefinierten inkrementierenden Betrag geändert werden.  
  
-   Die Position kann von einer beliebigen Anzahl geändert werden.  
  
-   Die Position kann auf einen bestimmten Wert geändert werden.  
  
### <a name="to-change-the-position-by-a-preset-amount"></a>So ändern Sie die Position um einen vordefinierten Wert  
  
1.  Verwenden der [SetStep](../mfc/reference/cprogressctrl-class.md#setstep) Memberfunktion Inkrement fest. Standardmäßig ist dieser Wert 10. Dieser Wert wird in der Regel als starteinstellungen für das Steuerelement festgelegt werden. Step-Wert kann negativ sein.  
  
2.  Verwenden der [StepIt](../mfc/reference/cprogressctrl-class.md#stepit) Memberfunktion versucht, die Position zu erhöhen. Dies bewirkt, dass das Steuerelement selbst neu zeichnet.  
  
    > [!NOTE]
    >  `StepIt`führt dazu, dass die Position, um zu umschließen. Angenommen, die einen Bereich von 1 -100, einen Schritt 20 und eine Position 90, `StepIt` wird die Position auf 10 festgelegt.  
  
### <a name="to-change-the-position-by-an-arbitrary-amount"></a>So ändern Sie die Position von einer beliebigen Anzahl  
  
1.  Verwenden der [OffsetPos](../mfc/reference/cprogressctrl-class.md#offsetpos) Member-Funktion, um die Position ändern. `OffsetPos`negative Werte akzeptiert.  
  
    > [!NOTE]
    >  `OffsetPos`, im Gegensatz zu `StepIt`, der die Position wird nicht umbrochen. Die neue Position wird angepasst, um die innerhalb des Bereichs zu gewährleisten.  
  
### <a name="to-change-the-position-to-a-specific-value"></a>So ändern Sie die Position auf einen bestimmten Wert  
  
1.  Verwenden der [Memberfunktion SetPos](../mfc/reference/cprogressctrl-class.md#setpos) Memberfunktion versucht, die Position auf einen bestimmten Wert festgelegt. Bei Bedarf wird angepasst, dass die neue Position innerhalb des Bereichs liegen.  
  
 In der Regel ist das Statussteuerelement ausschließlich für die Ausgabe verwendet. Verwenden Sie zum Abrufen der aktuellen Position ohne Angabe eines neuen Werts [GetPos](../mfc/reference/cprogressctrl-class.md#getpos).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CProgressCtrl](../mfc/using-cprogressctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

