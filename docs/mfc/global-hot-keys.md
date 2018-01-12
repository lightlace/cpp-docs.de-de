---
title: "Globale Abkürzungstasten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 82297507d8725e6292def759272f48d0d63e84b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="global-hot-keys"></a>Globale Abkürzungstasten
Eine globale Abkürzungstaste ist einem bestimmten, nicht untergeordneten Fenster zugeordnet. Er ermöglicht es dem Benutzer das Fenster von einem beliebigen Teil des Systems zu aktivieren. Eine Anwendung wird eine globale Abkürzungstaste für ein bestimmtes Fenster durch Senden der [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) Nachricht zu diesem Fenster. Z. B. wenn `m_HotKeyCtrl` ist die [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) Objekt und `pMainWnd` ist ein Zeiger auf das Fenster aktiviert werden, wenn die Zugriffstaste gedrückt wird, können Sie den folgenden Code den hot in Steuerelement mit dem angegebenen Schlüssel zugeordnet Das Fenster verweist `pMainWnd`.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]  
  
 Wenn der Benutzer eine globale Abkürzungstaste drückt, empfängt das angegebene Fenster ein [WM_SYSCOMMAND](http://msdn.microsoft.com/library/windows/desktop/ms646360) Nachricht, der angibt, **SC_HOTKEY** als Typ des Befehls. Diese Meldung wird auch das Fenster, das es empfängt aktiviert. Da diese Meldung keine Informationen für den genauen Schlüssel enthält, die gedrückt wurde, lässt verwenden diese Methode keine Unterscheidung zwischen verschiedenen Abkürzungstasten, die das gleiche Fenster zugeordnet werden können. Die Abkürzungstaste bleibt gültig, bis die Anwendung, die gesendet **WM_SETHOTKEY** beendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

