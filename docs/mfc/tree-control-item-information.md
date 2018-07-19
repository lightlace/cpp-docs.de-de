---
title: Informationen über die Elemente Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 724e9d7c4e0ee7db80f024c30e363612cb40fed1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385364"
---
# <a name="tree-control-item-information"></a>Informationen über die Elemente im Struktursteuerelement
Struktursteuerelemente ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) eine Reihe von Memberfunktionen, die Informationen zu den Elementen im Steuerelement abzurufen. Die [GetItem](../mfc/reference/ctreectrl-class.md#getitem) Memberfunktion ruft einiger oder aller Daten, die einem Element zugeordnet. Diese Daten können es sich um den Text des Elements, Status, Bilder, Anzahl der untergeordneten Elemente und einem anwendungsdefinierten 32-Bit-Datenwert enthalten. Es gibt auch eine [SetItem](../mfc/reference/ctreectrl-class.md#setitem) -Funktion, die einige oder alle Daten, die einem Element zugeordneten festlegen kann.  
  
 Die [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate), [GetItemText](../mfc/reference/ctreectrl-class.md#getitemtext), [GetItemData](../mfc/reference/ctreectrl-class.md#getitemdata), und [GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage) Memberfunktionen rufen einzelne Attribute von einem Element. Jede dieser Funktionen verfügt über eine entsprechende Set-Funktion für die Attribute eines Elements festlegen.  
  
 Die [GetNextItem](../mfc/reference/ctreectrl-class.md#getnextitem) Memberfunktion Ruft das Element der Struktur-Steuerelement, das die angegebene Beziehung zum aktuellen Element trägt. Diese Funktion kann ein Element übergeordneten, das nächste oder vorherige sichtbare Element der ersten untergeordneten Elements und usw. abrufen. Es gibt auch Memberfunktionen zum Traversieren der Struktur verwendet werden: [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem), [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem), [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem), [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem), [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem), [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem), [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem), [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem), [GetSelectedItem](../mfc/reference/ctreectrl-class.md#getselecteditem), und [GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem).  
  
 Die [Memberfunktion GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect) Memberfunktion Ruft das umschließende Rechteck für ein Strukturelement-Steuerelement ab. Die [GetCount](../mfc/reference/ctreectrl-class.md#getcount) und [GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount) Memberfunktionen abzurufen, die Anzahl der Elemente in einem Strukturansicht-Steuerelement und Anzahl der Elemente, die aktuell sichtbaren des Strukturansicht-Steuerelements im Fenster bzw. sind. Sie können sicherstellen, dass ein bestimmtes Element sichtbar, durch Aufrufen ist der [EnsureVisible](../mfc/reference/ctreectrl-class.md#ensurevisible) Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

