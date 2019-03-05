---
title: Festlegen einer Abkürzungstaste
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: a77aad4881acd04c6dabb6dce90acc01be2cfbc8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281277"
---
# <a name="setting-a-hot-key"></a>Festlegen einer Abkürzungstaste

Die Anwendung kann mithilfe die Informationen von einer Abkürzungstaste ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) Steuerelement auf zwei Arten:

- Richten Sie eine globale Abkürzungstaste für die Aktivierung eines nicht untergeordneten Fensters durch Senden einer [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) Nachricht an das Fenster aktiviert wird.

- Festlegen einer Abkürzungstaste threadspezifische durch Aufrufen der Windows-Funktion [RegisterHotKey](/windows/desktop/api/winuser/nf-winuser-registerhotkey).

## <a name="see-also"></a>Siehe auch

[Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
