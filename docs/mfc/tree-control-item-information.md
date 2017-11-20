---
title: "Informationen über die Elemente Struktur | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7a0747147f247f7400e2455fdf5f63e61378e96e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="tree-control-item-information"></a>Informationen über die Elemente im Struktursteuerelement
Struktursteuerelemente ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) eine Reihe von Memberfunktionen, die Informationen zu den Elementen im Steuerelement abzurufen. Die [GetItem](../mfc/reference/ctreectrl-class.md#getitem) Memberfunktion ruft einiger oder aller Daten, die einem Element zugeordnet. Diese Daten können es sich um den Text des Elements, Status, Bilder, Anzahl der untergeordneten Elemente und einem anwendungsdefinierten 32-Bit-Datenwert enthalten. Es gibt auch eine [SetItem](../mfc/reference/ctreectrl-class.md#setitem) -Funktion, die einige oder alle Daten, die einem Element zugeordneten festlegen kann.  
  
 Die [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate), [GetItemText](../mfc/reference/ctreectrl-class.md#getitemtext), [GetItemData](../mfc/reference/ctreectrl-class.md#getitemdata), und [GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage) Memberfunktionen rufen einzelne Attribute von einem Element. Jede dieser Funktionen verfügt über eine entsprechende Set-Funktion für die Attribute eines Elements festlegen.  
  
 Die [GetNextItem](../mfc/reference/ctreectrl-class.md#getnextitem) Memberfunktion Ruft das Element der Struktur-Steuerelement, das die angegebene Beziehung zum aktuellen Element trägt. Diese Funktion kann ein Element übergeordneten, das nächste oder vorherige sichtbare Element der ersten untergeordneten Elements und usw. abrufen. Es gibt auch Memberfunktionen zum Traversieren der Struktur verwendet werden: [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem), [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem), [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem), [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem), [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem), [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem), [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem), [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem), [GetSelectedItem](../mfc/reference/ctreectrl-class.md#getselecteditem), und [GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem).  
  
 Die [Memberfunktion GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect) Memberfunktion Ruft das umschließende Rechteck für ein Strukturelement-Steuerelement ab. Die [GetCount](../mfc/reference/ctreectrl-class.md#getcount) und [GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount) Memberfunktionen abzurufen, die Anzahl der Elemente in einem Strukturansicht-Steuerelement und Anzahl der Elemente, die aktuell sichtbaren des Strukturansicht-Steuerelements im Fenster bzw. sind. Sie können sicherstellen, dass ein bestimmtes Element sichtbar, durch Aufrufen ist der [EnsureVisible](../mfc/reference/ctreectrl-class.md#ensurevisible) Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

