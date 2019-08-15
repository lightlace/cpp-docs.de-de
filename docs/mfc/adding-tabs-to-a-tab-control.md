---
title: Hinzufügen von Registerkarten zum Registersteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
ms.openlocfilehash: 8915b3af083ebe318e8527b2f83099bf61e7e3ce
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509297"
---
# <a name="adding-tabs-to-a-tab-control"></a>Hinzufügen von Registerkarten zum Registersteuerelement

Fügen Sie nach dem Erstellen des Registerkarten-Steuer Elements ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) beliebig viele Registerkarten hinzu.

### <a name="to-add-a-tab-item"></a>So fügen Sie ein Registerkarten Element hinzu

1. Bereiten Sie eine [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) -Struktur vor.

1. Ruft [CTabCtrl:: InsertItem](../mfc/reference/ctabctrl-class.md#insertitem)auf und übergibt die Struktur.

1. Wiederholen Sie die Schritte 1 und 2 für zusätzliche Registerkarten Elemente.

Weitere Informationen finden Sie unter [Erstellen eines Register](/windows/win32/Controls/tab-controls) Karten-Steuer Elements in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
