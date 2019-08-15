---
title: Threadspezifische Abkürzungstasten
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
ms.openlocfilehash: 49bac6ac357924c26f131bbd8e1092cd74514167
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511137"
---
# <a name="thread-specific-hot-keys"></a>Threadspezifische Abkürzungstasten

Eine Anwendung legt eine Thread spezifische Hot-Taste ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) mithilfe der Windows `RegisterHotKey` -Funktion fest. Wenn der Benutzer eine Thread spezifische Hot-Taste drückt, stellt Windows eine [WM_HOTKEY](/windows/win32/inputdev/wm-hotkey) -Meldung an den Anfang der Nachrichten Warteschlange eines bestimmten Threads. Die WM_HOTKEY-Nachricht enthält den Code des virtuellen Schlüssels, den UMSCHALT Zustand und die benutzerdefinierte ID der bestimmten, gedrückten Taste. Eine Liste der virtuellen Standardschlüssel Codes finden Sie unter Winuser. h. Weitere Informationen zu dieser Methode finden Sie unter [RegisterHotKey](/windows/win32/api/winuser/nf-winuser-registerhotkey).

Beachten Sie, dass die im Aufruf `RegisterHotKey` von verwendeten verschiebungsstatusflags nicht mit denen übereinstimmen, die von der [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) -Member-Funktion zurückgegeben werden. `RegisterHotKey`Sie müssen diese Flags vor dem Aufrufen von übersetzen.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
