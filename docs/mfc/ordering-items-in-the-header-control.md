---
title: "Anordnen von Elementen im Headersteuerelement"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "DS_DRAGDROP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DS_DRAGDROP-Benachrichtigung"
  - "GetOrderArray-Methode"
  - "Headersteuerelemente, Anordnen von Elementen"
  - "OrderToIndex-Methode"
  - "Reihenfolge"
  - "Reihenfolge, Header-Steuerelemente"
  - "SetOrderArray-Methode"
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Anordnen von Elementen im Headersteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie [hinzugefügte Elemente zu einem Header\-Steuerelement](../mfc/adding-items-to-the-header-control.md) haben, können Sie Informationen über die Reihenfolge mit den folgenden Features bearbeiten oder abrufen:  
  
-   [CHeaderCtrl::GetOrderArray](../Topic/CHeaderCtrl::GetOrderArray.md) und [CHeaderCtrl::SetOrderArray](../Topic/CHeaderCtrl::SetOrderArray.md)  
  
     Ruft ab und legt die Reihenfolge von links nach rechts von Kopfzeilenelementen fest.  
  
-   [CHeaderCtrl::OrderToIndex](../Topic/CHeaderCtrl::OrderToIndex.md).  
  
     Ruft den Indexwert für ein bestimmtes Headerelement ab.  
  
 Zusätzlich zu den aufgeführten Memberfunktionen können das Format `HDS_DRAGDROP` den Benutzer den Drag & Drop\-Kopfzeilenelementen innerhalb des Header\-Steuerelements.  Weitere Informationen finden Sie unter [Gewähren der Drag & Drop\-Unterstützung für Kopfzeilen\-Elemente](../mfc/providing-drag-and-drop-support-for-header-items.md).  
  
## Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)