---
title: Festlegen einer Abkürzungstaste
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: 7b49f24039b130f74693e7567f5287476126f225
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511220"
---
# <a name="setting-a-hot-key"></a>Festlegen einer Abkürzungstaste

Die Anwendung kann die Informationen, die von einem Hot Key-Steuerelement ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) bereitgestellt werden, auf eine von zwei Arten verwenden:

- Richten Sie einen globalen Hot Key zum Aktivieren eines nicht untergeordneten Fensters ein, indem Sie eine [WM_SETHOTKEY](/windows/win32/inputdev/wm-sethotkey) -Nachricht an das zu aktivierende Fenster senden.

- Richten Sie einen Thread spezifischen Hotkey ein, indem Sie die Windows-Funktion [RegisterHotKey](/windows/win32/api/winuser/nf-winuser-registerhotkey)aufrufen.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
