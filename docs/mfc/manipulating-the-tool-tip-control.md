---
title: Bearbeiten des QuickInfo-Steuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- CToolTipCtrl class [MFC], manipulating tool tip attributes
- tool tips [MFC], attributes
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
ms.openlocfilehash: 2624f6c1da0e771b34d590d787c00e53ee6ff62e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625925"
---
# <a name="manipulating-the-tool-tip-control"></a>Bearbeiten des QuickInfo-Steuerelements

Klasse `CToolTipCtrl` stellt eine Gruppe von der Members-Funktionen, die die verschiedenen Attribute des steuern die `CToolTipCtrl` -Objekt und das QuickInfo-Fenster.

Die ursprüngliche, Popup- und Wiederholungsdauern für QuickInfo-Fenster können festgelegt und, die mit Aufrufen von abgerufen [GetDelayTime](../mfc/reference/ctooltipctrl-class.md#getdelaytime) und [SetDelayTime](../mfc/reference/ctooltipctrl-class.md#setdelaytime).

Ändern Sie die Darstellung der QuickInfo-Fenster mit den folgenden Funktionen:

- [GetMargin](../mfc/reference/ctooltipctrl-class.md#getmargin) und [SetMargin](../mfc/reference/ctooltipctrl-class.md#setmargin) ab oder legt die Breite zwischen dem QuickInfo-Rahmen und das Tool den QuickInfo-Text.

- [GetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#getmaxtipwidth) und [SetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#setmaxtipwidth) ab oder legt die maximale Breite des Tools QuickInfo-Fensters.

- [GetTipBkColor](../mfc/reference/ctooltipctrl-class.md#gettipbkcolor) und [SetTipBkColor](../mfc/reference/ctooltipctrl-class.md#settipbkcolor) ab oder legt die Hintergrundfarbe des Tools QuickInfo-Fensters.

- [GetTipTextColor](../mfc/reference/ctooltipctrl-class.md#gettiptextcolor) und [SetTipTextColor](../mfc/reference/ctooltipctrl-class.md#settiptextcolor) ab oder legt die Textfarbe des Tools QuickInfo-Fensters.

In der Reihenfolge für das QuickInfo-Steuerelement über wichtige Meldungen, z. B. WM_LBUTTONXXX-Nachrichten benachrichtigt werden müssen Sie die Nachrichten auf Ihre QuickInfo-Steuerelement weiterleiten. Die beste Methode für dieses Relay wird ein Aufruf von [CToolTipCtrl:: RelayEvent](../mfc/reference/ctooltipctrl-class.md#relayevent)in die `PreTranslateMessage` Funktion das besitzende Fenster. Das folgende Beispiel veranschaulicht eine mögliche Methode (vorausgesetzt, das QuickInfo-Steuerelement heißt `m_ToolTip`):

[!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/cpp/manipulating-the-tool-tip-control_1.cpp)]

Um sofort eine QuickInfo-Fenster zu entfernen, rufen Sie die [Pop](../mfc/reference/ctooltipctrl-class.md#pop) Member-Funktion.

## <a name="see-also"></a>Siehe auch

[Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

