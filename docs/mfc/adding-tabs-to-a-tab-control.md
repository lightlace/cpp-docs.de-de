---
title: Hinzufügen von Registerkarten zum Registersteuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86032bd3d1ce10221cb5d8094e4ba6de866e1eea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342852"
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

