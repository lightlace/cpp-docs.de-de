---
title: Hinzufügen von Registerkarten zum Registersteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
ms.openlocfilehash: f769de7bcf3e410cca717c17237d1e49ef8562c9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293588"
---
# <a name="adding-tabs-to-a-tab-control"></a>Hinzufügen von Registerkarten zum Registersteuerelement

Nach dem Erstellen des Registersteuerelements ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), fügen Sie so viele Registerkarten, wie Sie benötigen.

### <a name="to-add-a-tab-item"></a>Hinzufügen ein Registerkartenelements

1. Vorbereiten einer [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) Struktur.

1. Rufen Sie [CTabCtrl:: InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), indem Sie die Struktur.

1. Wiederholen Sie die Schritte 1 und 2 für zusätzliche Registerelemente.

Weitere Informationen finden Sie unter [erstellen ein Registerkarten-Steuerelement](/windows/desktop/Controls/tab-controls) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
