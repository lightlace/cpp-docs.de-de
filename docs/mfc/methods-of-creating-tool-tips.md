---
title: Methoden zum Erstellen von QuickInfos
ms.date: 11/04/2016
helpviewer_keywords:
- CToolTipCtrl class [MFC], creating tool tips
- tool tips [MFC], tool tip controls
- tool tips [MFC], creating
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
ms.openlocfilehash: 80c826b3c9a4f9e24ebd201eaa9d775f9ad9f8cf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663813"
---
# <a name="methods-of-creating-tool-tips"></a>Methoden zum Erstellen von QuickInfos

MFC stellt drei Klassen zum Erstellen und verwalten das Tool QuickInfo-Steuerelement: [CWnd](../mfc/reference/cwnd-class.md), [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md), [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) und [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md). Der QuickInfo-Memberfunktionen in diesen Klassen zu umschließen der allgemeinen Windows-Steuerungs-API. Klasse `CToolBarCtrl` und Klasse `CToolTipCtrl` Klasse abgeleitet sind `CWnd`.

`CWnd` bietet vier Memberfunktionen zum Erstellen und Verwalten von QuickInfos: [EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips), [CancelToolTips](../mfc/reference/cwnd-class.md#canceltooltips), [FilterToolTipMessage](../mfc/reference/cwnd-class.md#filtertooltipmessage), und [OnToolHitTest ](../mfc/reference/cwnd-class.md#ontoolhittest). Finden Sie weitere Informationen, wie sie QuickInfos implementieren diese individuelle Memberfunktionen aus.

Wenn Sie erstellen eine Symbolleiste mit `CToolBarCtrl`, können Sie die QuickInfos für diese Symbolleiste direkt über die folgenden Member-Funktionen implementieren: [GetToolTips](../mfc/reference/ctoolbarctrl-class.md#gettooltips) und [SetToolTips](../mfc/reference/ctoolbarctrl-class.md#settooltips). Finden Sie unter diese einzelne Memberfunktionen und [behandeln Tool Tipp Benachrichtigungen](../mfc/handling-tool-tip-notifications.md) für Weitere Informationen, wie sie QuickInfos implementieren.

Die `CToolTipCtrl` Klasse stellt die Funktionalität Windows allgemeine QuickInfo-Steuerelements bereit. Ein einzelnes QuickInfo-Steuerelement kann es sich um Informationen zu mehr als ein Tool bereit. Ein Tool ist entweder ein Fenster, z. B. eines untergeordneten Fensters oder Steuerelements einen anwendungsdefinierten rechteckigen Bereich im Clientbereich eines Fensters. Die [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md) Klasse leitet sich von `CToolTipCtrl` und stellt zusätzliche visuellen Stilen und Funktionen bereit.

## <a name="see-also"></a>Siehe auch

[Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

