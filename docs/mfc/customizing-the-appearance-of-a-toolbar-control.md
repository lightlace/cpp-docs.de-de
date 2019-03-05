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
ms.openlocfilehash: 8a0db3299ebb54d226edc1434dedbc6a04eb9b00
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302337"
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>Anpassen der Darstellung eines Symbolleisten-Steuerelements

Klasse `CToolBarCtrl` bietet viele Formatvorlagen, die die Darstellung (und manchmal das Verhalten) des Symbolleistenobjekts zu beeinflussen. Ändern Sie die Symbolleistenobjekt durch Festlegen der `dwCtrlStyle` Parameter, der die `CToolBarCtrl::Create` (oder `CToolBar::CreateEx`) Member-Funktion, die bei der Erstellung der Symbolleisten-Steuerelement.

Die folgenden Stile wirken sich auf den "3D" Aspekt der Symbolleisten-Schaltflächen und die Positionierung der Text der Schaltfläche:

- **TBSTYLE_FLAT** erstellt eine flache Symbolleiste, in denen sowohl die Symbolleiste und die Schaltflächen transparent sind. Text der Schaltfläche wird unter Bitmaps für Schaltflächen angezeigt. Wenn dieses Format verwendet wird, wird die Schaltfläche unterhalb des Cursors automatisch hervorgehoben.

- **TBSTYLE_TRANSPARENT** erstellt eine transparente Symbolleiste. Klicken Sie in eine transparente Symbolleiste die Symbolleiste ist transparent, aber die Schaltflächen sind nicht. Text der Schaltfläche wird unter Bitmaps für Schaltflächen angezeigt.

- **TBSTYLE_LIST** stellen Schaltfläche Text rechts neben der Schaltfläche Bitmaps.

> [!NOTE]
>  Um zu verhindern, dass "Repaint" Probleme auftreten, die **TBSTYLE_FLAT** und **TBSTYLE_TRANSPARENT** Stile festgelegt werden, bevor das Symbolleistenobjekt sichtbar ist.

Die folgenden Stile bestimmen, ob die Symbolleiste einem Benutzer ermöglicht zu Position der einzelne Schaltflächen in einem Symbolleistenobjekt, das mithilfe von Drag & drop:

- **TBSTYLE_ALTDRAG** können Benutzer eine Symbolleisten-Schaltfläche Position ändern, durch Ziehen bei gedrückter Alt-Taste. Wenn dieses Format nicht angegeben wird, muss der Benutzer die UMSCHALTTASTE beim Ziehen einer Schaltfläche aufweisen.

    > [!NOTE]
    >  Die **CCS_ADJUSTABLE** Stil muss angegeben werden, um die Schaltflächen der Symbolleiste für den das Ziehen zu aktivieren.

- **TBSTYLE_REGISTERDROP** generiert **TBN_GETOBJECT** Benachrichtigung Zielobjekte Nachrichten anfordern gelöscht werden, wenn der Mauszeiger über der Symbolleisten-Schaltflächen bewegt.

Die verbleibenden Formatvorlagen wirken sich auf visuelle und nicht visuelle Aspekte des Symbolleistenobjekts:

- **TBSTYLE_WRAPABLE** erstellt eine Symbolleiste, die mehrere Zeilen von Schaltflächen enthalten kann. Schaltflächen der Symbolleiste können in die nächste Zeile "umschließen" werden, wird die Symbolleiste nicht breit genug, um alle Schaltflächen auf der gleichen Zeile einzuschließen. Wrapping tritt auf, auf die Trennung und nongroup Grenzen.

- **TBSTYLE_CUSTOMERASE** generiert **NM_CUSTOMDRAW** Benachrichtigung bei der Verarbeitung von Nachrichten **WM_ERASEBKGND** Nachrichten.

- **TBSTYLE_TOOLTIPS** erstellt ein QuickInfo-Steuerelement, mit denen eine Anwendung beschreibenden Text für die Schaltflächen auf der Symbolleiste angezeigt.

Eine vollständige Liste der Toolbar-Stile und erweiterte Stile, finden Sie unter [Toolbar-Steuerelement und Button-Stile](/windows/desktop/Controls/toolbar-control-and-button-styles) und [Symbolleiste Erweiterte Stile](/windows/desktop/Controls/toolbar-extended-styles) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
