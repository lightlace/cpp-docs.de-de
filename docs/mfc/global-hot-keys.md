---
title: Globale Abkürzungstasten
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
ms.openlocfilehash: 59918648ea24fd1e2a86ca786de3081cd6cca2df
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508568"
---
# <a name="global-hot-keys"></a>Globale Abkürzungstasten

Eine globale Hot-Taste ist einem bestimmten nicht untergeordneten Fenster zugeordnet. Es ermöglicht dem Benutzer, das Fenster in jedem Teil des Systems zu aktivieren. Eine Anwendung legt eine globale Hot-Taste für ein bestimmtes Fenster fest, indem die [WM_SETHOTKEY](/windows/win32/inputdev/wm-sethotkey) -Nachricht an dieses Fenster gesendet wird. Wenn `m_HotKeyCtrl` beispielsweise das [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) -Objekt ist und `pMainWnd` ein Zeiger auf das Fenster ist, das aktiviert werden soll, wenn die Hot-Taste gedrückt wird, können Sie den folgenden Code verwenden, um die im-Steuerelement angegebene Hot-Taste mit dem Fenster zuzuordnen, auf das von gezeigt wird. `pMainWnd`.

[!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]

Wenn der Benutzer eine globale Hot-Taste drückt, empfängt das angegebene Fenster eine [WM_SYSCOMMAND](/windows/win32/menurc/wm-syscommand) -Meldung, die **SC_HOTKEY** als Typ des Befehls angibt. Diese Meldung aktiviert auch das Fenster, in dem Sie empfangen wird. Da diese Nachricht keine Informationen über die exakte Taste enthält, die gedrückt wurde, lässt die Verwendung dieser Methode nicht zu, dass unterschiedliche heiße Tasten unterscheiden, die an dasselbe Fenster angefügt werden können. Die Hot-Taste bleibt gültig, bis die Anwendung, die **WM_SETHOTKEY** gesendet hat, beendet wird.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
