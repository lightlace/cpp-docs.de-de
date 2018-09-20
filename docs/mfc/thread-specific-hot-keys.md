---
title: Threadspezifische Abkürzungstasten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e54fbb2709f5f5bb6d01c279cb369b91dbfcaed
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372161"
---
# <a name="thread-specific-hot-keys"></a>Threadspezifische Abkürzungstasten

Eine Anwendung festlegt, eine Thread-spezifische Abkürzungstaste ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) mithilfe der Windows `RegisterHotKey` Funktion. Wenn der Benutzer eine Thread-spezifische Abkürzungstaste drückt, sendet Windows eine [WM_HOTKEY](/windows/desktop/inputdev/wm-hotkey) Nachricht an den Anfang der Warteschlange für einen bestimmten Thread-Nachrichten. Die WM_HOTKEY-Nachricht enthält den virtueller Tastencode, UMSCHALT-Status und eine benutzerdefinierte-ID des jeweiligen Abkürzungstaste, die gedrückt wurde. Eine Liste der standardmäßige virtuelle Tastencodes finden Sie unter "Winuser.h". Weitere Informationen zu dieser Methode finden Sie unter [RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309).

Beachten, die den Umschaltzustand kennzeichnet, die im Aufruf von verwendet `RegisterHotKey` sind nicht identisch mit denen vom der [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) Memberfunktion; Sie müssen diese Flags vor dem Aufruf übersetzt `RegisterHotKey`.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

