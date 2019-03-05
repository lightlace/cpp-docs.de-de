---
title: Informationen über die Elemente im Struktursteuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
ms.openlocfilehash: e0eb8af4fbbb6f59c0dda75ec3705183ce916350
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288895"
---
# <a name="tree-control-item-information"></a>Informationen über die Elemente im Struktursteuerelement

Struktursteuerelemente ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) eine Reihe von Memberfunktionen, die Informationen über die Elemente im Steuerelement abzurufen. Die [GetItem](../mfc/reference/ctreectrl-class.md#getitem) Memberfunktion Ruft ab, einige oder alle Daten, die einem Element zugeordnet. Diese Daten können es sich um den Text des Elements, Status, Bilder, die Anzahl der untergeordneten Elemente und einen anwendungsdefinierten 32-Bit-Daten-Wert enthalten. Es gibt auch eine [SetItem](../mfc/reference/ctreectrl-class.md#setitem) -Funktion, die einige oder alle Daten, die einem Element zugeordneten festlegen kann.

Die [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate), [GetItemText](../mfc/reference/ctreectrl-class.md#getitemtext), [GetItemData](../mfc/reference/ctreectrl-class.md#getitemdata), und [GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage) Memberfunktionen Abrufen einzelner Attribute von einem Element. Jede dieser Funktionen verfügt über eine entsprechende Set-Funktion für die Attribute eines Elements festlegen.

Die [GetNextItem](../mfc/reference/ctreectrl-class.md#getnextitem) Memberfunktion Ruft das Element der Struktur-Steuerelement, das die angegebene Beziehung zum aktuellen Element trägt. Diese Funktion kann ein Element des übergeordneten, das nächste oder vorherige sichtbare Element, das erste untergeordnete Element und usw. abgerufen werden. Es gibt auch Memberfunktionen zum Durchlaufen der Struktur: [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem), [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem), [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem), [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem), [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem), [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem), [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem), [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem), [GetSelectedItem](../mfc/reference/ctreectrl-class.md#getselecteditem), und [ GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem).

Die [Memberfunktion GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect) Memberfunktion Ruft das umschließende Rechteck für ein Strukturelement-Steuerelement. Die [GetCount](../mfc/reference/ctreectrl-class.md#getcount) und [GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount) Memberfunktionen abzurufen, die Anzahl der Elemente in einem Strukturansicht-Steuerelement und eine Anzahl von Elementen, die derzeit sichtbar in der Strukturansicht im Fenster bzw. sind. Sie können sicherstellen, dass ein bestimmtes Element sichtbar, durch den Aufruf ist der [EnsureVisible](../mfc/reference/ctreectrl-class.md#ensurevisible) Member-Funktion.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
