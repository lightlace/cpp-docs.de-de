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
ms.openlocfilehash: 1f68fb62335219ea498163e6124c8e91e49f2938
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511025"
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>QuickInfos in Fenstern, die nicht von CFrameWnd abgeleitet sind

In dieser Artikel Familie wird das Aktivieren von Quick Infos für Steuerelemente beschrieben, die in einem Fenster enthalten sind, das nicht von [CFrameWnd](../mfc/reference/cframewnd-class.md)abgeleitet ist. Im Artikel [Quick](../mfc/toolbar-tool-tips.md) Infos Quick Infos finden Sie Informationen zu Quick Infos für Steuerelemente `CFrameWnd`in einer.

Zu den in dieser Artikel Familie behandelten Themen gehören:

- [Erstellen von QuickInfos](../mfc/enabling-tool-tips.md)

- [Behandeln der TTN_NEEDTEXT-Benachrichtigung für QuickInfos](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)

- [Die ToolTipText-Struktur](../mfc/tooltiptext-structure.md)

Quick Infos werden automatisch für Schaltflächen und andere Steuerelemente angezeigt, die in einem von `CFrameWnd`abgeleiteten übergeordneten Fenster enthalten sind. Dies liegt daran `CFrameWnd` , dass über einen Standard Handler für die [TTN_GETDISPINFO](/windows/win32/Controls/ttn-getdispinfo) -Benachrichtigung verfügt, der **TTN_NEEDTEXT** -Benachrichtigungen von QuickInfo-Steuerelementen verarbeitet, die Steuerelementen zugeordnet sind

Dieser Standard Handler wird jedoch nicht aufgerufen, wenn die **TTN_NEEDTEXT** -Benachrichtigung von einem QuickInfo-Steuerelement gesendet wird, das einem Steuerelement in einem Fenster `CFrameWnd`zugeordnet ist, das kein ist, z. b. ein Steuerelement in einem Dialogfeld oder in einer Formularansicht. Daher ist es erforderlich, dass Sie eine Handlerfunktion für die **TTN_NEEDTEXT** -Benachrichtigungs Meldung bereitstellen, um Quick Infos für untergeordnete Steuerelemente anzuzeigen.

Die standardmäßigen Quick Infos, die für Windows von [CWnd:: EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips) bereitgestellt werden, sind mit keinem Text verknüpft. Zum Abrufen von Text für die QuickInfo, die angezeigt werden soll, wird die **TTN_NEEDTEXT** -Benachrichtigung an das übergeordnete Fenster des QuickInfo-Steuer Elements gesendet, kurz bevor das QuickInfo-Fenster angezeigt wird. Wenn kein Handler für diese Nachricht vorhanden ist, um dem *pszText* -Member der **ToolTipText** -Struktur einen Wert zuzuweisen, wird für die QuickInfo kein Text angezeigt.

## <a name="see-also"></a>Siehe auch

[QuickInfos](../mfc/tool-tips.md)
