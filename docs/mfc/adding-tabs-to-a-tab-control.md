---
title: Hinzufügen von Registerkarten zum Registersteuerelement | Microsoft-Dokumentation
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
ms.openlocfilehash: cb8caad0b7d1f632a2d97e4ea6bda7c93a2b4d74
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218296"
---
# <a name="adding-tabs-to-a-tab-control"></a>Hinzufügen von Registerkarten zum Registersteuerelement
Nach dem Erstellen des Registersteuerelements ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), fügen Sie so viele Registerkarten, wie Sie benötigen.  
  
### <a name="to-add-a-tab-item"></a>Hinzufügen ein Registerkartenelements  
  
1.  Vorbereiten einer [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Struktur.  
  
2.  Rufen Sie [CTabCtrl:: InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), indem Sie die Struktur.  
  
3.  Wiederholen Sie die Schritte 1 und 2 für zusätzliche Registerelemente.  
  
 Weitere Informationen finden Sie unter [erstellen ein Registerkarten-Steuerelement](/windows/desktop/Controls/tab-controls) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

