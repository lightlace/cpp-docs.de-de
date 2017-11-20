---
title: "Threadspezifische Abkürzungstasten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 75c3b5356277e227832ecc94a9f6b70cc15f3a71
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="thread-specific-hot-keys"></a>Threadspezifische Abkürzungstasten
Eine Anwendung legt eine threadspezifische Abkürzungstaste ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) mithilfe der Windows **RegisterHotKey** Funktion. Wenn der Benutzer eine threadspezifische Abkürzungstaste drückt, sendet Windows eine [WM_HOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646279) Nachricht an den Anfang der Warteschlange für einen bestimmten Thread-Nachrichten. Die **WM_HOTKEY** Nachricht enthält den virtueller Tastencode, die UMSCHALT-Status und die benutzerdefinierte-ID des jeweiligen Abkürzungstaste, die gedrückt wurde. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie unter Winuser.h. Weitere Informationen zu dieser Methode finden Sie unter [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
 Hinweis, das den Umschaltzustand kennzeichnet, die im Aufruf verwendet **RegisterHotKey** sind nicht identisch mit denen zurückgegebene der [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) Memberfunktion; Sie müssen diese Flags, die vor dem Aufrufen von Übersetzen**RegisterHotKey**.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

