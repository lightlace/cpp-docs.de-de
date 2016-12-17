---
title: "Informationen &#252;ber die Elemente im Struktursteuerelement"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl-Klasse, Elementinformationen"
  - "Struktursteuerelemente, Elementinformationen"
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Informationen &#252;ber die Elemente im Struktursteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tree\-Steuerelemente \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) gelten einige Memberfunktionen, die Informationen über Elemente im Steuerelement abrufen.  Die Memberfunktion [GetItem](../Topic/CTreeCtrl::GetItem.md) ruft einiger oder aller Daten ab, die einem Element zugeordnet werden.  Diese Daten können den Text des Elements, Zustand, Bilder, Anzahl untergeordnete Elemente sowie einen 32\-Bit\-Datenwert anwendungsdefinierten enthalten.  Es ist auch eine [SetItem](../Topic/CTreeCtrl::SetItem.md)\-Funktion, die einige oder festlegen kann alle Daten, die einem Element zugeordnet werden.  
  
 [GetItemState](../Topic/CTreeCtrl::GetItemState.md), [GetItemText](../Topic/CTreeCtrl::GetItemText.md), [GetItemData](../Topic/CTreeCtrl::GetItemData.md) und [GetItemImage](../Topic/CTreeCtrl::GetItemImage.md)\-Memberfunktionen rufen einzelne Attribute eines Elements ab.  Jede dieser Funktionen verfügt über eine entsprechende festgelegte Funktion zum Festlegen der Attribute eines Elements.  
  
 Die Memberfunktion [GetNextItem](../Topic/CTreeCtrl::GetNextItem.md) ruft das Strukturansicht\-Steuerelement\-Element ab, das die angegebene Beziehung dem aktuellen Element enthält.  Diese Funktion kann das übergeordnete Element eines Elements, die nächste oder vorherige sichtbare Element, das erste untergeordnete Element abrufen, u. a.  Es sind außerdem Memberfunktionen, um die Struktur zu durchlaufen: [GetRootItem](../Topic/CTreeCtrl::GetRootItem.md), [GetFirstVisibleItem](../Topic/CTreeCtrl::GetFirstVisibleItem.md), [GetNextVisibleItem](../Topic/CTreeCtrl::GetNextVisibleItem.md), [GetPrevVisibleItem](../Topic/CTreeCtrl::GetPrevVisibleItem.md), [GetChildItem](../Topic/CTreeCtrl::GetChildItem.md), [GetNextSiblingItem](../Topic/CTreeCtrl::GetNextSiblingItem.md), [GetPrevSiblingItem](../Topic/CTreeCtrl::GetPrevSiblingItem.md), [GetParentItem](../Topic/CTreeCtrl::GetParentItem.md), [GetSelectedItem](../Topic/CTreeCtrl::GetSelectedItem.md) und [GetDropHilightItem](../Topic/CTreeCtrl::GetDropHilightItem.md).  
  
 Die Memberfunktion [GetItemRect](../Topic/CTreeCtrl::GetItemRect.md) ruft das umschließende Rechteck für ein Strukturansicht\-Steuerelement\-Element ab.  Die [GetCount](../Topic/CTreeCtrl::GetCount.md) und [GetVisibleCount](../Topic/CTreeCtrl::GetVisibleCount.md)\-Memberfunktionen rufen eine Anzahl der Elemente in einer Strukturansicht und eine Anzahl der Elemente, die im Fenster des Strukturansicht\-Steuerelements gerade sichtbar sind, jeweils ab.  Sie können sicherstellen, dass ein bestimmter Punkt sichtbar ist, indem er die [EnsureVisible](../Topic/CTreeCtrl::EnsureVisible.md)\-Memberfunktion aufruft.  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)