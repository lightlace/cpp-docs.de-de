---
title: Hinzufügen von Elementen zum Headersteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
ms.openlocfilehash: 897612c6d5ac96704cc0a945df65146e6a01480a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264377"
---
# <a name="adding-items-to-the-header-control"></a>Hinzufügen von Elementen zum Headersteuerelement

Nach dem Erstellen Ihrer Kopfzeilen-Steuerelements ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) in das übergeordnete Fenster, wie viele Headerelemente hinzufügen, "" wie Sie benötigen: in der Regel eine pro Spalte.

### <a name="to-add-a-header-item"></a>Ein Headerelement hinzufügen

1. Vorbereiten einer [HD_ITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) Struktur.

1. Rufen Sie [InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), indem Sie die Struktur.

1. Wiederholen Sie die Schritte 1 und 2 für zusätzliche Elemente.

Weitere Informationen finden Sie unter [Hinzufügen eines Elements zu einem Kopfzeilen-Steuerelement](/windows/desktop/Controls/header-controls) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
