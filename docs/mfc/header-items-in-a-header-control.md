---
title: "Headerelemente in einem Headersteuerelement"
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
  - "CHeaderCtrl-Klasse, Headerelemente in"
  - "Steuerelemente [MFC], Header"
  - "Headersteuerelemente, Headerelemente in"
  - "Headerelemente in Headersteuerelementen"
ms.assetid: ac79ef1f-a671-4ab2-93e9-b1aa016a48bf
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Headerelemente in einem Headersteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie haben beträchtliches Kontrolle über das Aussehen und Verhalten der Kopfzeilenelemente, die ein Header\-Steuerelement \([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)\) besteht.  Jedes Headerelement kann eine Zeichenfolge, ein Bitmapbild, ein Bild von einer entsprechenden Bildliste oder anwendungsdefinierte einen 32\-Bit\-Wert haben, der ihm zugeordnet ist.  Die Zeichenfolge, die Bitmap oder das Bild wird im Headerelement angezeigt.  
  
 Sie können die Darstellung und den Inhalt von neuen Elementen anpassen, wenn dieser erstellt werden, indem ein Aufruf [CHeaderCtrl::InsertItem](../Topic/CHeaderCtrl::InsertItem.md) wird oder ein vorhandenes Element, mit einem Aufruf von [CHeaderCtrl::GetItem](../Topic/CHeaderCtrl::GetItem.md) und zu [CHeaderCtrl::SetItem](../Topic/CHeaderCtrl::SetItem.md).  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Anpassen der Darstellung des Kopfzeilenelements](../mfc/customizing-the-header-item-s-appearance.md)  
  
-   [Reihenfolgenelemente im Header\-Steuerelement](../mfc/ordering-items-in-the-header-control.md)  
  
-   [Gewähren der Drag & Drop\-Unterstützung für die Kopfzeilenelemente](../mfc/providing-drag-and-drop-support-for-header-items.md)  
  
-   [Verwenden der Bildlisten mit Header\-Steuerelementen](../mfc/using-image-lists-with-header-controls.md)  
  
## Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)