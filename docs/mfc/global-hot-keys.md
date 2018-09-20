---
title: Globale Abkürzungstasten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d749fad0fabf8ae99bba129caee399e3f93ff9af
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443851"
---
# <a name="global-hot-keys"></a>Globale Abkürzungstasten

Eine globale Abkürzungstaste bezieht sich auf einem bestimmten, nicht untergeordneten Fenster. Dadurch wird den Benutzer das Fenster von einem beliebigen Teil des Systems zu aktivieren. Eine Anwendung wird eine globale Abkürzungstaste für ein bestimmtes Fenster durch Senden der [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) -Meldung an das Fenster. Z. B. wenn `m_HotKeyCtrl` ist die [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) Objekt und `pMainWnd` ist ein Zeiger an das Fenster aktiviert wird, wenn die Abkürzungstaste gedrückt wird, können Sie den folgenden Code die "Hot" in Steuerelement mit dem angegebenen Schlüssel zuordnen Das Fenster zeigt `pMainWnd`.

[!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]

Wenn der Benutzer eine globale Abkürzungstaste drückt, empfängt das angegebene Fenster ein [WM_SYSCOMMAND](/windows/desktop/menurc/wm-syscommand) Nachricht, der angibt, **SC_HOTKEY** als Typ des Befehls. Diese Meldung wird auch das Fenster, das er empfängt aktiviert. Da diese Meldung keine Informationen für den exakten Schlüssel enthält, die gedrückt wurde, lässt das mit dieser Methode nicht zu unterscheiden zwischen verschiedenen Abkürzungstasten, die mit dem gleichen Fenster angefügt werden können. Die Abkürzungstaste gültig bleibt, bis die Anwendung, die gesendet **WM_SETHOTKEY** beendet wird.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

