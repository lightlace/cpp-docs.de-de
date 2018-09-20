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
ms.openlocfilehash: d5f9a9ab897a91fe886a1ba3ad46fe8fab94d94c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416590"
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

