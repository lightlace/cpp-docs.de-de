---
title: QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind
ms.date: 11/04/2016
helpviewer_keywords:
- enabling tool tips [MFC]
- TOOLTIPTEXT structure [MFC]
- Help [MFC], tool tips for controls
- TTN_NEEDTEXT message [MFC]
- controls [MFC], tool tips
- handler functions [MFC], tool tips
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
ms.openlocfilehash: 3d44f2c503b689360f040e6804d319c331d5c0ca
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260659"
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind

Diese Artikelreihe behandelt aktiviert QuickInfos für Steuerelemente in einem Fenster, die nicht von abgeleitet ist [CFrameWnd](../mfc/reference/cframewnd-class.md). Der Artikel [Symbolleisten-QuickInfo](../mfc/toolbar-tool-tips.md) enthält Informationen über QuickInfos für Steuerelemente in einem `CFrameWnd`.

In dieser Gruppe von Artikeln behandelten Themen gehören:

- [Erstellen von QuickInfos](../mfc/enabling-tool-tips.md)

- [Behandeln der TTN_NEEDTEXT-Benachrichtigung für QuickInfos](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)

- [TOOLTIPTEXT-Struktur](../mfc/tooltiptext-structure.md)

Tool-Tipps werden automatisch angezeigt, für Schaltflächen und anderen Steuerelementen in einem übergeordneten Fenster abgeleitet `CFrameWnd`. Grund hierfür ist, `CFrameWnd` verfügt über eine Standard-Handler für die [TTN_GETDISPINFO](/windows/desktop/Controls/ttn-getdispinfo) Benachrichtigung, die behandelt **TTN_NEEDTEXT** Benachrichtigungen vom Tool Tipp Steuerelemente-Steuerelementen zugeordnet.

Jedoch diese Standard-Handler wird nicht aufgerufen, wenn die **TTN_NEEDTEXT** Benachrichtigung über ein einem Steuerelement in einem Fenster, die nicht zugeordnete QuickInfo-Steuerelement eine `CFrameWnd`, z. B. ein Steuerelement auf ein Dialogfeld oder eine Formularansicht. Daher ist es erforderlich, Sie bieten eine Handlerfunktion für die **TTN_NEEDTEXT** Benachrichtigung zum Anzeigen von QuickInfos für die untergeordneten Steuerelemente.

Die standardmäßigen QuickInfos für Fenster, indem [CWnd:: EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips) keinen Text zugeordnet. Zum Abrufen der Text der QuickInfo angezeigt werden, die **TTN_NEEDTEXT** Benachrichtigung wird an das QuickInfo-Steuerelement des übergeordneten Fenster gesendet, kurz bevor das QuickInfo-Fenster angezeigt wird. Wenn es ist kein Handler für diese Nachricht einige Wert zuzuweisen der *PszText* Mitglied der **TOOLTIPTEXT** Struktur, die kein Text für die QuickInfo angezeigt werden.

## <a name="see-also"></a>Siehe auch

[QuickInfos](../mfc/tool-tips.md)
