---
title: Anpassen der Darstellung eines Symbolleisten-Steuerelements
ms.date: 11/04/2016
f1_keywords:
- TBSTYLE_
helpviewer_keywords:
- flat toolbars
- CToolBar class [MFC], styles
- transparent toolbars
- TBSTYLE_ styles [MFC]
- CToolBarCtrl class [MFC], object styles
- toolbar controls [MFC], style
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
ms.openlocfilehash: 590f0dce6c50ee6d0ca30c4c68e21787563bd686
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508728"
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>Anpassen der Darstellung eines Symbolleisten-Steuerelements

Die `CToolBarCtrl` -Klasse stellt viele Stile bereit, die sich auf die Darstellung (und gelegentlich auch das Verhalten) des Toolbar-Objekts auswirken. Ändern Sie das Symbolleisten Objekt, `dwCtrlStyle` indem Sie den `CToolBarCtrl::Create` -Parameter `CToolBar::CreateEx`der (oder)-Element Funktion festlegen, wenn Sie das ToolBar-Steuerelement erstmalig erstellen.

Die folgenden Stile beeinflussen den 3D-Aspekt der Symbolleisten Schaltflächen und die Platzierung des Schaltflächen Texts:

- **TBSTYLE_FLAT** Erstellt eine flache Symbolleiste, auf der die Symbolleiste und die Schaltflächen transparent sind. Schaltflächen Text wird unter Bitmaps der Schaltfläche angezeigt. Wenn dieser Stil verwendet wird, wird die Schaltfläche unterhalb des Cursors automatisch hervorgehoben.

- **TBSTYLE_TRANSPARENT** Erstellt eine transparente Symbolleiste. In einer transparenten Symbolleiste ist die Symbolleiste transparent, aber die Schaltflächen sind nicht. Schaltflächen Text wird unter Bitmaps der Schaltfläche angezeigt.

- **TBSTYLE_LIST** Platziert den Schaltflächen Text rechts neben Schaltflächen-Bitmaps.

> [!NOTE]
>  Um Repaint-Probleme zu vermeiden, sollten die Stile **TBSTYLE_FLAT** und **TBSTYLE_TRANSPARENT** festgelegt werden, bevor das Symbolleisten Objekt sichtbar ist.

Die folgenden Stile bestimmen, ob die Symbolleiste einem Benutzer ermöglicht, einzelne Schaltflächen in einem Toolbar-Objekt mithilfe von Drag & Drop neu zu positionieren:

- **TBSTYLE_ALTDRAG** Ermöglicht Benutzern das Ändern der Position einer Symbolleisten-Schaltfläche durchziehen, während die Alt-Taste gedrückt wird. Wenn dieser Stil nicht angegeben wird, muss der Benutzer beim Ziehen einer Schaltfläche die UMSCHALTTASTE gedrückt halten.

    > [!NOTE]
    >  Der **CCS_ADJUSTABLE** -Stil muss angegeben werden, damit die Symbolleisten Schaltflächen gezogen werden können.

- **TBSTYLE_REGISTERDROP** Generiert **TBN_GETOBJECT** -Benachrichtigungs Meldungen, um Drop Target-Objekte anzufordern, wenn der Mauszeiger über die Symbolleisten Schaltflächen

Die verbleibenden Stile wirken sich auf visuelle und nicht visuelle Aspekte des Toolbar-Objekts aus:

- **TBSTYLE_WRAPABLE** Erstellt eine Symbolleiste, die mehrere Zeilen mit Schaltflächen aufweisen kann. Symbolleisten Schaltflächen können mit der nächsten Zeile "Wrap" werden, wenn die Symbolleiste zu schmal wird, um alle Schaltflächen in derselben Zeile einzuschließen. Das umwickeln erfolgt bei Trennungs-und nicht Gruppen Grenzen.

- **TBSTYLE_CUSTOMERASE** Generiert **NM_CUSTOMDRAW** -Benachrichtigungs Meldungen bei der Verarbeitung von **WM_ERASEBKGND** -Nachrichten.

- **TBSTYLE_TOOLTIPS** Erstellt ein QuickInfo-Steuerelement, das eine Anwendung verwenden kann, um beschreibenden Text für die Schaltflächen auf der Symbolleiste anzuzeigen.

Eine umfassende Liste der Symbolleisten Stile und erweiterter Stile finden Sie unter Symbolleisten- [Steuerelement und Schalt](/windows/win32/Controls/toolbar-control-and-button-styles) Flächen Formate und [Erweiterte Stile der Symbolleiste](/windows/win32/Controls/toolbar-extended-styles) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
