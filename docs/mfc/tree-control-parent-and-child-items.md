---
title: "&#220;bergeordnete und untergeordnete Elemente in einem Struktursteuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Untergeordnete Elemente in Struktursteuerelementen"
  - "CTreeCtrl-Klasse, Übergeordnete und untergeordnete Elemente"
  - "Übergeordnete Elemente in CTreeCtrl"
  - "Struktursteuerelemente, Übergeordnete und untergeordnete Elemente"
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# &#220;bergeordnete und untergeordnete Elemente in einem Struktursteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jedes Element in einem der Strukturansicht \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) kann eine Liste mit Unterelementen, die über untergeordnete Elemente bezeichnet werden, zugeordnet.  Ein Element, das ein oder mehrere untergeordnete Elemente hat, wird ein übergeordnetes Element aufgerufen.  Ein untergeordnetes Element wird unterhalb des übergeordneten Elements angezeigt und wird eingezogen, um zu kennzeichnen ist untergeordnet übergeordnete Element.  Ein Element, das kein übergeordnetes Element hat, ist in der Hierarchie und wird als Stammelement bezeichnet.  
  
 Zu jedem Zeitpunkt kann der Zustand der Liste eines übergeordneten Elements der untergeordneter Elemente entweder erweitert oder reduziert werden.  Wenn der Zustand erweitert wird, werden die untergeordneten Elemente unterhalb des übergeordneten Elements angezeigt.  Wenn sie reduziert sind, werden die untergeordneten Elemente nicht angezeigt.  In der Liste der automatisch zwischen den erweiterten und reduzierten Zustände, wenn Benutzer auf das übergeordnete Element öffnen oder, wenn das übergeordnete Element das **TVS\_HASBUTTONS** Format hat, wenn der Benutzer auf die Schaltfläche klickt, die dem übergeordneten Element zugeordnet ist.  Eine Anwendung kann die untergeordnete Elemente erweitern oder reduzieren, indem Sie die Memberfunktion [Erweitern](../Topic/CTreeCtrl::Expand.md) verwendet.  
  
 Sie ein Element einem Strukturansicht hinzu, indem Sie die Memberfunktion [InsertItem](../Topic/CTreeCtrl::InsertItem.md) aufrufen.  Diese Funktion gibt ein Handle des Typs **HTREEITEM** zurück, der das Element eindeutig identifiziert.  Wenn Sie ein Element hinzufügen, müssen Sie das Handle des übergeordneten Elements des neuen Elements angeben.  Wenn Sie **NULL** oder das **TVI\_ROOT**\-Wert anstelle eines Handles des übergeordneten Elements in der Struktur unter [TVINSERTSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb773452) oder im `hParent`\-Parameter angeben, wird das Element als Stammelement hinzugefügt.  
  
 Eine Strukturansicht sendet eine Benachrichtigung [TVN\_ITEMEXPANDING](http://msdn.microsoft.com/library/windows/desktop/bb773537), wenn die Liste eines übergeordneten Elements von untergeordneten Elementen im Begriff ist erweitert werden oder reduziert werden.  Die Benachrichtigung erhalten Sie die Möglichkeit, die Änderungen zu unterbinden oder alle Attribute des übergeordneten Elements festlegen, die vom Zustand der Liste untergeordneter Elemente abhängen.  Nachdem Sie den Zustand der Liste geändert hat, sendet das Tree\-Steuerelement eine Benachrichtigung. [TVN\_ITEMEXPANDED](http://msdn.microsoft.com/library/windows/desktop/bb773533)  
  
 Wenn eine Liste untergeordneter Elemente erweitert wird, wird sie relativ zum übergeordneten Element eingezogen.  Sie können die Größe des Einzugs, indem Sie die [SetIndent](../Topic/CTreeCtrl::SetIndent.md) festlegen oder Memberfunktion, verwenden die aktuelle Menge abrufen, indem Sie die Memberfunktion [GetIndent](../Topic/CTreeCtrl::GetIndent.md) verwenden.  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)