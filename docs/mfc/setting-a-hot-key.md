---
title: Festlegen einer Abkürzungstaste
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: ebaddb4a64a4d9d47b82fd36f118c74527554e53
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893223"
---
# <a name="setting-a-hot-key"></a>Festlegen einer Abkürzungstaste

Die Anwendung kann mithilfe die Informationen von einer Abkürzungstaste ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) Steuerelement auf zwei Arten:

- Richten Sie eine globale Abkürzungstaste für die Aktivierung eines nicht untergeordneten Fensters durch Senden einer [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) Nachricht an das Fenster aktiviert wird.

- Festlegen einer Abkürzungstaste threadspezifische durch Aufrufen der Windows-Funktion [RegisterHotKey](/windows/desktop/api/winuser/nf-winuser-registerhotkey).

## <a name="see-also"></a>Siehe auch

[Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

