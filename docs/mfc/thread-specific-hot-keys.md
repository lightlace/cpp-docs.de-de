---
title: Threadspezifische Abkürzungstasten | Microsoft Docs
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
ms.openlocfilehash: 14da7f0e5b0adbe72b6705700c1e9298751bc345
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953608"
---
# <a name="thread-specific-hot-keys"></a>Threadspezifische Abkürzungstasten
Eine Anwendung legt eine threadspezifische Abkürzungstaste ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) mithilfe der Windows `RegisterHotKey` Funktion. Wenn der Benutzer eine threadspezifische Abkürzungstaste drückt, sendet Windows eine [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) Nachricht an den Anfang der Warteschlange für einen bestimmten Thread-Nachrichten. Die WM_HOTKEY-Nachricht enthält den virtueller Tastencode UMSCHALT-Status und benutzerdefinierte-ID des jeweiligen Abkürzungstaste, die gedrückt wurde. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie unter Winuser.h. Weitere Informationen zu dieser Methode finden Sie unter [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
 Beachten Sie, das den Umschaltzustand kennzeichnet im Aufruf verwendet `RegisterHotKey` sind nicht identisch mit denen zurückgegebene der [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) Memberfunktion; stehen Ihnen übersetzt diese Flags vor dem Aufruf `RegisterHotKey`.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

