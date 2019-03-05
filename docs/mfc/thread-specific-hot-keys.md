---
title: Threadspezifische Abkürzungstasten
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
ms.openlocfilehash: a54aa878b0160132157879127f8335c951e91785
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290988"
---
# <a name="thread-specific-hot-keys"></a>Threadspezifische Abkürzungstasten

Eine Anwendung festlegt, eine Thread-spezifische Abkürzungstaste ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) mithilfe der Windows `RegisterHotKey` Funktion. Wenn der Benutzer eine Thread-spezifische Abkürzungstaste drückt, sendet Windows eine [WM_HOTKEY](/windows/desktop/inputdev/wm-hotkey) Nachricht an den Anfang der Warteschlange für einen bestimmten Thread-Nachrichten. Die WM_HOTKEY-Nachricht enthält den virtueller Tastencode, UMSCHALT-Status und eine benutzerdefinierte-ID des jeweiligen Abkürzungstaste, die gedrückt wurde. Eine Liste der standardmäßige virtuelle Tastencodes finden Sie unter "Winuser.h". Weitere Informationen zu dieser Methode finden Sie unter [RegisterHotKey](/windows/desktop/api/winuser/nf-winuser-registerhotkey).

Beachten, die den Umschaltzustand kennzeichnet, die im Aufruf von verwendet `RegisterHotKey` sind nicht identisch mit denen vom der [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) Memberfunktion; Sie müssen diese Flags vor dem Aufruf übersetzt `RegisterHotKey`.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
