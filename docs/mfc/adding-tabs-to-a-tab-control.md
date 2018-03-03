---
title: "Hinzufügen von Registerkarten zum Registersteuerelement | Microsoft Docs"
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
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 46012a265c1ecefa7af63f829be22e6132e036cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="adding-tabs-to-a-tab-control"></a>Hinzufügen von Registerkarten zum Registersteuerelement
Nach dem Erstellen des Registersteuerelements ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), fügen Sie so viele Registerkarten wie erforderlich.  
  
### <a name="to-add-a-tab-item"></a>So fügen Sie ein Registerkartenelement hinzu  
  
1.  Vorbereiten einer [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Struktur.  
  
2.  Rufen Sie [CTabCtrl:: InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), die Struktur übergeben wird.  
  
3.  Wiederholen Sie die Schritte 1 und 2 für zusätzliche Registerkartenelemente.  
  
 Weitere Informationen finden Sie unter [ein Registerkarten-Steuerelement erstellen](http://msdn.microsoft.com/library/windows/desktop/bb760550) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

