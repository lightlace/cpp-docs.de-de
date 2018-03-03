---
title: Anordnen von Elementen im Headersteuerelement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DS_DRAGDROP
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 48adbc53ad0e4974edd86d3f8a96d74214093dda
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ordering-items-in-the-header-control"></a>Anordnen von Elementen im Headersteuerelement
Sobald Sie haben [hinzugefügten Elemente zu einem Headersteuerelement](../mfc/adding-items-to-the-header-control.md), können Sie bearbeiten oder Abrufen von Informationen zu deren Reihenfolge mit den folgenden Funktionen:  
  
-   [CHeaderCtrl:: GetOrderArray](../mfc/reference/cheaderctrl-class.md#getorderarray) und [CHeaderCtrl::SetOrderArray](../mfc/reference/cheaderctrl-class.md#setorderarray)  
  
     Ruft ab, und die links-nach-rechts-Reihenfolge der Headerelemente.  
  
-   [CHeaderCtrl::OrderToIndex](../mfc/reference/cheaderctrl-class.md#ordertoindex).  
  
     Ruft den Indexwert für ein bestimmtes Headerelement ab.  
  
 Zusätzlich zu den vorherigen Memberfunktionen der `HDS_DRAGDROP` Stil ermöglicht dem Benutzer, die Drag & drop innerhalb des Headersteuerelements Headerelemente. Weitere Informationen finden Sie unter [Bereitstellen von Drag-and-Drop-Unterstützung für Headerelemente](../mfc/providing-drag-and-drop-support-for-header-items.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)

