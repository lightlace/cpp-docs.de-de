---
title: Übergeordnete und untergeordnete Elemente in einem Struktursteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- parent items in CTreeCtrl [MFC]
- child items in tree control [MFC]
- CTreeCtrl class [MFC], parent and child items
- tree controls [MFC], parent and child items
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
ms.openlocfilehash: 5a02194ccef8eca81971bb4e8ae24d859e578bcc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513972"
---
# <a name="tree-control-parent-and-child-items"></a>Übergeordnete und untergeordnete Elemente in einem Struktursteuerelement

Jedes Element in einem Struktur Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) kann eine Liste von unter Elementen enthalten, die als untergeordnete Elemente bezeichnet werden. Ein Element, das über ein oder mehrere untergeordnete Elemente verfügt, wird als übergeordnetes Element bezeichnet. Unterhalb des übergeordneten Elements wird ein untergeordnetes Element angezeigt, das eingerückt wird, um anzugeben, dass es dem übergeordneten Element untergeordnet ist. Ein Element, das über kein übergeordnetes Element verfügt, befindet sich oben in der Hierarchie und wird als Stamm Element bezeichnet.

Der Status der Liste der untergeordneten Elemente eines übergeordneten Elements kann zu einem beliebigen Zeitpunkt entweder erweitert oder reduziert werden. Wenn der Zustand erweitert ist, werden die untergeordneten Elemente unter dem übergeordneten Element angezeigt. Wenn Sie reduziert ist, werden die untergeordneten Elemente nicht angezeigt. Die Liste wechselt automatisch zwischen den erweiterten und reduzierten Zuständen, wenn der Benutzer auf das übergeordnete Element doppelklickt, oder, wenn das übergeordnete Element den **TVS_HASBUTTONS** -Stil hat, wenn der Benutzer auf die Schaltfläche klickt, die dem übergeordneten Element zugeordnet ist. Eine Anwendung kann die untergeordneten Elemente [mithilfe der Erweiterungs Element Funktion erweitern oder](../mfc/reference/ctreectrl-class.md#expand) reduzieren.

Sie fügen ein Element zu einem Struktur Steuerelement hinzu, indem Sie die [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) -Member-Funktion aufrufen. Diese Funktion gibt ein Handle des **HTREEITEM** -Typs zurück, der das Element eindeutig identifiziert. Wenn Sie ein Element hinzufügen, müssen Sie das Handle des übergeordneten Elements des neuen Elements angeben. Wenn Sie **null** oder den **TVI_ROOT** -Wert anstelle eines übergeordneten Element Handles in der [TVINSERTSTRUCT](/windows/win32/api/commctrl/ns-commctrl-tvinsertstructw) -Struktur oder dem *hParent* -Parameter angeben, wird das Element als Stamm Element hinzugefügt.

Ein Struktur Steuerelement sendet eine [TVN_ITEMEXPANDING](/windows/win32/Controls/tvn-itemexpanding) -Benachrichtigungs Meldung, wenn die Liste der untergeordneten Elemente eines übergeordneten Elements erweitert oder reduziert wird. Die Benachrichtigung bietet Ihnen die Möglichkeit, die Änderung zu verhindern oder Attribute des übergeordneten Elements festzulegen, die vom Status der Liste der untergeordneten Elemente abhängen. Nachdem der Status der Liste geändert wurde, sendet das Struktur Steuerelement eine [TVN_ITEMEXPANDED](/windows/win32/Controls/tvn-itemexpanded) -Benachrichtigungs Meldung.

Wenn eine Liste von untergeordneten Elementen erweitert wird, wird Sie relativ zum übergeordneten Element eingerückt. Sie können den Einzug mithilfe der [setIndent](../mfc/reference/ctreectrl-class.md#setindent) -Element Funktion festlegen oder den aktuellen Betrag mithilfe der [GetIndent](../mfc/reference/ctreectrl-class.md#getindent) -Member-Funktion abrufen.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
